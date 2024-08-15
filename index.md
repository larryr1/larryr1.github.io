# Larry Rowe - Developer Portfolio
## About Me
Ever since I was old enough to use a computer, I had interests that came and went, as everyone does. However, one interest lingered, which was seeking the answer to **how does box this of circut boards work?**

Eventually, that interest expressed itself in the form of programming. I began tinkering in Chrome on school computers in the Inspect Element window, writing my own little sites with pages and tricking my friends into thinking I deleted google.
One of the first programs I ever wrote was a calculator in the form of a batch script, on a Windows Vista laptop my grandmother had given me.

I began to take on more advanced projects, with the aim of discovering new technologies and wanting to see my own creation appear on someone else's screen. I developed my first large project in 8th grade, the Patrol Leaders Council Database.

## The PLC Database
[Link to Website](https://plc.glitch.me)

The PLC database had the original purpose of communicating meeting plans to the leadership board of my Boy Scout Troop, with later added option for showing "games" that have been entered on the website.

The website runs with a Node.JS backend, serving HTTP requests with the `express.js` package. It uses some basic templating to fill in some placeholder values on some pages, and has an API that allows for the frontend to fetch relevant data about meetings and games.
Even though database is in the name, there isn't a database in the traditional sense. The website's data is edited by manually adding or removing JSON files for each meeting or game. These files are indexed when the server starts.

The data retrieval for the games works slightly different. The games are markdown files, but contain a special header format that tell the server what the title and description of the game is to be displayed when any users view the main list of games.

The website doesn't use a framework of any kind. I wrote each view by hand using the Bootstrap CSS utilites.

## The PLC Library Database

Ha! This one actually uses a database.

The PLC Library Database had the original purpose of being an all-in-one suite for managing our Troop's library, including checking in, checking out, printing labels, and accepting checkout requests from users.

This project unfortunately never saw completion because I lost interest and moved on with more important things. The functionality I was able to implement includes data persistence via a SQLite database and Single Sign-On using Auth0 as the identity provider.
