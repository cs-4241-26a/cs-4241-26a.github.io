*[Course Assignments & Due Dates](https://github.com/cs-4241-26a/cs-4241-26a.github.io/blob/main/calendar.md)*

# Webware

Tuesday / Friday 2:00–3:50   
Unity Hall Room 420

Course Staff
---
*Instructor*: Charlie Roberts (@cdroberts)  
*PLA*: Harrison DiAmbrosio (@hadiambrosio)  
*PLA*: Cole Golding (@cmgolding)  
*PLA*: Keagan Hitt (@kjhitt)  
*PLA*: Anastasios Pagiatakis (@ajpagiatakis)

Office Hours
---
- Monday: 2-4 w/Cole, 7-9 w/ Harrison (in Discord)
- Tuesday: 12-2 w/Cole
- Wednesday: 10-12 and 4-6 w/ Harrison
- Thursday: 12-2 w/Cole, 2-4 w/ Harrison, 4-6 w/Cole (in Discord)
- Friday: 10AM - 12PM w/Charlie in FL B20

Office hours will be announced on Discord immediately prior to beginning. For office hours with course PLAs the location will default to Fuller Labs A22.

All course staff will also spend time on Discord answering questions asynchronously. Whenever possible, please post questions *publicly* in Discord so everyone can learn from the answers... and there's a good chance students in the class might be able to help with technical questions as well. My in-person office hours are from 10AM-12PM on Friday, in Fuller Labs B20... please stop by! Some good reasons to stop by in-person office hours include:

- We can't debug your problems over Discord
- Brainstorming on final project / assignment ideas
- You're interested in learning more about [my research](http://charlie-roberts.com)
- You want to talk about art / music / graphics / programming more generally
- You want to tell me about your research
- You'd like to sit and work a bit with me/other students nearby in case questions popup (space permitting)
- Anything else, really!

The PLAs are available during their office hours for questions / help on any course related content.

Course Description
---

This course explores computational, aesthetic, and user-centered aspects of designing and developing applications for the web. 
Topics include: web scripting and markup languages, design of browser-based interfaces, client/server network architectures, web accessibility,
creative coding in the browser, and the environmental impact of web design and development.

All students will complete a *full-stack* (client + server + database integration) application as a final group project in the course; 
in addition, several smaller assignments (completed individually) will also build towards full stack development.

Students will be expected to use Git in this class and all assignments will be turned in using GitHub. That said, GitHub is increasingly problematic in terms of uptime and terms of service, check out alternatives like [Codeberg](https://codeberg.org) and [SourceHut](https://sourcehut.org) as alternatives for your personal projects. Please begin familiarizing yourselves with Git if you don't have prior experience with it; it will not be taught in the course. The course PLAs can provide help with Git for those who need it, so please take advantage of their expertise!

Learning Goals
---

After successful completion of this course, you will be able to:

- Critically evaluate and deconstruct the design and technical characteristics of web applications.
- Create functional and accessible web applications, including front-end and back-end components.
- Understand how to use the web for creative activities, and how to embed a bit of whimsy into websites.

Required Texts
---
There are no required texts for this course. Required readings will be taken from various online resources. For those who can't wait to start digging into JavaScript:

- [Eloquent JavaScript](https://eloquentjavascript.net/) is rapidly becoming one of the most popular JavaScript books on the web.
- [You Don't Know JS](https://github.com/getify/You-Dont-Know-JS) is where most of our assigned readings on JavaScript will come from.

Assignments
---
Assignments are the core of this course. Each assignment will focus on a particular aspect of web design and development, such as database integration, 
component libraries, server development, or creative coding. Assignment are due by the start of class on the date listed on the calendar, e.g. 
if the due date is on a Friday, the assignment is due by 1:59 PM Friday.

Programming Languages
---

We'll be primarily using [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) in both the browser and with [node.js](http://nodejs.org/) 
to develop web applications in this course. We'll be using node.js for simplicity and language consistency across client / server development. [Deno](deno.land) and [Bun](https://bun.sh/) are node.js alternatives that are worth exploring.

Development Tools
---
You can use whatever editor you like in this class. I primarily use vim alongside tmux in the terminal, and it is nice to know this combination if you
anticipate doing a lot of remote server programming, as every Linux / macOS server (and increasingly Windows as well) will have these tools installed.

But if you've never used vim (or its arch nemesis emacs), I recommend using [VSCode](https://code.visualstudio.com), which is free and available for most platforms. [VSCodium](https://vscodium.com) is a virtually identical product that removes Microsoft's telemetry. 

Discussion / Questions
---
This term we will be using Discord for class discussion, in order to get you help fast and efficiently from classmates and the course staff. 
Rather than emailing questions to staff, post your questions to Discord to ensure you get a timely response, and to ensure that our responses 
can be seen by others who may have the same question you do. In general, most communication for the course will happen through Discord.

You will be emailed a link to join the Discord server for this course. It will likely be the last email you receive related to this course; 
please keep a close eye on the announcements on the server to make sure you don't miss information on assignments.

Grading
---

Your course grade comes from three parts:

- Homework assignments (55%)
- Project (35%)
- Quizzes (10%)

I reserve the right to adjust the above if needed. Quizzes will be based on the assigned readings for each class. They will be short (3--5 questions) and are *designed
to be as easy as possible assuming you've done the reading*, and take no more than five minutes. I welcome accomodation requests for quizzes (!), but also encourage you to try 
taking the first one before scheduling alternative times to take the quiz, just to get a feel for how simple they are. Your lowest quiz grade for the term will be dropped and not counted towards your grade.

You can turn in one assignment late during the course of the term; please DM the course staff in Discord (@admin) for a small extension. If it is a personal matter you wish to discuss it's fine to only contact the instructor. *It is much better to submit partially complete work than nothing at all.* Tell us what you have completed and you will get partial credit... even just making an empty pull request for an assignment will get you some points!

### Assignment Achievements

Unless otherwise noted, meeting the minimum requirements for an assignment will earn a B (86%).

You may earn up to additional 20 points via optional achievements from either *technical* or *design* achievements. They are an opportunity for you to take an active role in your learning and assessment; 
you get to choose which achievements are most interesting to complete.
Achievement points can both boost your grade up to an A and also make up for points 
that you might have lost in regards to the minimum requirements for an assignment.

For example, say your base grade was an 80%, which would mean that you were docked 6% off the minimum assignment requirements. 
If you then completed 10 points of achievements, you would receive an 90% (A) on the assignment. If you completed all 20 achievement points, you would still get a 100%, even after missing some points on the primary assignment requirements.
*The maximum grade for any one assignment is 100%*, even if you get a perfect score on the minimum requirements and all achievements.

*The success of your assignment achievements depends on how well you describe them in your README.*
Well formatted text, images, and concise and clear descriptions are helpful. Every README must include an Achievements section, even if none are attempted.

Make sure any frameworks and libraries you choose to employ **do not** interfere with the underlying intellectual challenge of the assignment. 
If I ask you to write a HTTP server and you use a package that provides a server in one line of code, 
you'll lose points instead of gaining them. Our aim is to open the black box of these packages in the scope of this course, 
so that when you encounter them later, you will better understand what they're doing for you.

Academic Integrity
---
In this class, students may not look at any previous versions of a course assignment or project, regardless of how it is posted. 

Students are likewise forbidden from facilitating other students, current or future, in plagiarism or cheating. 
However, collaboration is encouraged in this class. There are many ways in which you can assist your fellow students without giving them code and answers.
Please feel free to answer low-level coding questions and to help your classmates troubleshoot their code.
But do not provide significant chunks of code; for example, providing an entire server that you've written is not allowed.
We highly encourage everyone to spend time in the course Discord server, both asking and answering questions about any topics from the course.

LLM Use
---
The use of LLMs for significant code generation is not allowed, and any minor use of LLMs (code completion etc.) should be disclosed in the README of individual assignments. This class is an opportunity to learn the underlying technologies of the web, please don't use shortcuts that don't involve research (looking up how to do things online) or collaboration (reaching out to fellow students and course staff for help). If you have questions about what would cross the line on LLM use, please ask in the Discord.

Acknowledgements
---

Some aspects of these course materials were adapted from materials by:
- Lane Harrison
- Gary Pollice
