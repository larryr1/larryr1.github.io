# SCPA Event Display

The SCPA Event Display is displayed on several displays around our school campus. It uses the API on our school webpage to get the latest events that are posted, and the event display shows the next upcoming event.

This project consists of three individual projects:
* The frontend for the display.
* The frontend for the admin dashboard.
* The backend to serve both frontends.

The server was designed to run in a Windows Server IIS site but can be run anywhere Node.JS and NPM are available.

## Application Frameworks

Each component of the project uses different frameworks.

The display frontend was written in React, with the Bootstrap style utilities.  When using the create-react-app tooling, I discovered it was deprecated.

Since create-react-app was deprecated, I created the admin frontend with Vite. Vite allows me an easier developing experience by being able to configure proxy URLs
that point to my development server.

## How the Data is Retrieved

Every 5 seconds, the server makes the API request to get the events. Every second, the clients make a request to the server to get the latest events.
I chose this approach of relaying the data so that the school webpage's server wasn't overloaded by an API request from every client. Kind of the same way
you wouldn't give clients your API key and have them make requests on your behalf.

## How the Data is Stored

For storing configuration set by the user, the server uses a package called NeDB. It provides a mongo-like API for interfacing with collections stored in files.
The server creates and uses two separate files for data, one to hold application settings `settings.db` and one to hold the application users `users.db`.

## Pictures
Picture of the main display
![Main display](https://github.com/larryr1/larryr1.github.io/blob/main/projects/scpa-event/scpa-event-main.png?raw=true)
