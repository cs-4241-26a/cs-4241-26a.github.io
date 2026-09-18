# Server
To setup this project:
- Run `npm init vite` and make a new Svelte + JavaScript project.
- `cd` into the new directory, and run `npm install` to get all the Vite dependencies
- Get our express / websocket dependencies: `npm install express vite-express`

```js
const express = require('express')
const cors    = require('cors')
const ViteExpress = require('vite-express')
const app = express()

const todos = [
  { name:'buy groceries', completed:false }
]

app.use( express.json() )

app.use( (req,res, next) => {
  console.log( req.url )
  next()
})

// this will most likely be 'build' or 'public'
//app.use( express.static( 'dist' ) )

app.get( '/read', ( req, res ) => res.json( todos ) )

app.post( '/add', ( req,res ) => {
  todos.push( req.body )
  res.json( todos )
})

app.post( '/change', function( req,res ) {
  const idx = todos.findIndex( v => v.name === req.body.name )
  todos[ idx ].completed = req.body.completed
  
  res.sendStatus( 200 )
})

ViteExpress.listen( app, process.env.PORT || 3000 )
```



# Svelte
http://svelte.dev
- Uses code generation to create a small, optimized application
- Not made by Facebook(!)

## edit our App.svelte file
A file to load/display data from our server:

```html
// turns off Svelte 5 features
<svelte:options runes={false} />

<script>
  const getTodos = function() {
    const p = fetch( 'http://localhost:3000/read', {
      method:'GET' 
    })
    .then( response => response.json() )
    .then( json => {
      console.log(json)
      return json 
    })
 
    return p
  }
  
  let promise = getTodos()
</script>
  
{#await promise then todos}
  <ul>

  {#each todos as todo}
    <li>{todo.name} : <input type='checkbox' todo={todo.name} checked={todo.completed}></li>
  {/each}

  </ul>
{/await}  
```

Go ahead and call `npm run dev` in the project directory; this will start both the express server and the Svelte server. Note we're running them on different ports!

The part inside the `<script>` tag should look fairly normal. Outside of it is pretty weird looking though. The first line `{#await promise then todos}` basically is saying. Additionally, it's also saying "Everytime the promise resolves (re)create this list." Then, we start an unordered list `<ul>`. Next we're saying "for each todo in our todos variable, create a list item." We can see that we can insert JavaScript expressions inside of the `{}` characters, similar to how in ES6 we can put them expressions between `${ }` inside of template strings.
  
If you look at the `package.json` file included in the template, you'll see there's a `build` script. Use `npm run build` to compile the Svelte application (make sure you run `npm i` before compiling for the first time). You'll also need to install the `express` and `body-parser` packages, and then start the server using `node server.js`.
  
## adding new todos (reactive programming)
Here's where the magic happens:

```html
<script>
  const getTodos = function() {
    const p = fetch( 'http:localhost:3000/read', {
      method:'GET' 
    })
    .then( response => response.json() )
    .then( json => {
      console.log(json)
      return json 
    })
 
    return p
  }

  const addTodo = function( e ) {
    const todo = document.querySelector('input').value
    promise = fetch( 'http://localhost:3000/add', {
      method:'POST',
      body: JSON.stringify({ name:todo, completed:false }),
      headers: { 'Content-Type': 'application/json' }
    })
    .then( response => response.json() )
  }
  
  let promise = getTodos()
  </script>


<input type='text' />
<button on:click={addTodo}>add todo</button>

{#await promise then todos}
  <ul>

  {#each todos as todo}
    <li>{todo.name} : <input type='checkbox' todo={todo.name} checked={todo.completed} on:click={toggle}></li>
  {/each}

  </ul>
{/await}
```

In the above code we're adding the `addTodo` function and a button that triggers it. The magic is that, 
simply by redefining our `promise`. our list is recreated everytime we add a new todo. The UI is *reactive* to changes in the underlying data. 
OK, let's finish by adding a checkbox to toggle whether each todo item has been completed.


```html
<script>
  const getTodos = function() {
    const p = fetch( 'http://localhost:3000/read', {
      method:'GET' 
    })
    .then( response => response.json() )
    .then( json => {
      console.log(json)
      return json 
    })
 
    return p
  }

  const addTodo = function( e ) {
    const todo = document.querySelector('input').value
    promise = fetch( 'http://localhost:3000/add', {
      method:'POST',
      body: JSON.stringify({ name:todo, completed:false }),
      headers: { 'Content-Type': 'application/json' }
    })
    .then( response => response.json() )
  }

  const toggle = function( e ) {
    fetch( 'http://localhost:3000/change', {
      method:'POST',
      body: JSON.stringify({ name:e.target.getAttribute('todo'), completed:e.target.checked }),
      headers: { 'Content-Type': 'application/json' }
    })
  }

  let promise = getTodos()
</script>

<input type='text' />
<button on:click={addTodo}>add todo</button>

{#await promise then todos}
  <ul>

  {#each todos as todo}
    <li>{todo.name} : <input type='checkbox' todo={todo.name} checked={todo.completed} on:click={toggle}></li>
  {/each}

  </ul>
{/await}
```

Here we're simply submitting a POST to request whenever each checkbox is checked/unchecked to update the data on the server. The UI is automatically changed via normal HTML behavior, however, the UI will also reflect changes to the data when the page is refreshed.

## Wrapping up
Once your project is working, you'll need to complete a few extra steps to get it ready for distribution.

1. Run `npx vite build` from within the `client` directory. This will create a folder named `dist` containing your `index.html` page and all your compiled Svelte widgets.
2. Uncomment the line to use `express.static` in the server and make sure it points to the right folder that you compiled in step 1. The easiest solution here is probably to just place the `dist` folder in the same location as your server file.
3. If you just run the express server now, the project should still work without needing the Svelte dev server to run. However, if you transfer it to a server (glitch, heroku etc.) the routes will fail because they're pointing at `localhost`. You've got a couple of options to fix this:  
    - Go into the javascript that Svelte compiled for you (in `/dist/assets`) and do a quick find and replace to remove 'http://localhost:3000'.
    - Replace the hostname of any URLs in fetch commands with `http://${window.location.host}/get`, replacing 'get' with the route. This will automatically use the correct rul for all routes. You'll then need to recompile the Svelte project and recopy the build folder into your server directory.
