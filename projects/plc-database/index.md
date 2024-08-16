# The PLC Database
[Link to Website](https://plc.glitch.me)

The PLC database had the original purpose of communicating meeting plans to the leadership board of my Boy Scout Troop, with later added option for showing "games" that have been entered on the website.

The website runs with a Node.JS backend, serving HTTP requests with the `express.js` package. It uses some basic templating to fill in some placeholder values on some pages, and has an API that allows for the frontend to fetch relevant data about meetings and games.
Even though database is in the name, there isn't a database in the traditional sense. The website's data is edited by manually adding or removing JSON files for each meeting or game. These files are indexed when the server starts.

The data retrieval for the games works slightly different. The games are markdown files, but contain a special header format that tell the server what the title and description of the game is to be displayed when any users view the main list of games.

The website doesn't use a framework of any kind. I wrote each view by hand using the Bootstrap CSS utilites.

## Pictures
Home Page
![Home Page Image](https://larryr1.github.io/projects/plc-database/homepage.png)

Meeting Page
![Meeting Page Image](https://larryr1.github.io/projects/plc-database/meeting_page.png)

Check out the website for yourself at [https://plc.glitch.me](https://plc.glitch.me). It may take a moment to startup.
