# SCPA Event Display

The SCPA Event Display is displayed on several displays around our school campus. It uses the API on our school webpage to get the latest events that are posted, and the event display shows the next upcoming event. It features an admin interface that allows you to (at the time of writing) edit and arrange the messages that are shown below the latest event on the display.

You can see from the tabs on the admin dashboard that I'm planning to add other admin configuration options, such as:
* Creating other users and assign them permissions,
* Managing settings related to the display of events,
* Tracking points for groups of students called "house points."

This project consists of three individual projects:
* The frontend for the display.
* The frontend for the admin dashboard.
* The backend to serve both frontends.

The server was designed to run in a Windows Server IIS site but can be run anywhere Node.JS and NPM are available.

## Application Frameworks

Each component of the project uses different frameworks.

The display frontend was written in React, with the Bootstrap style utilities. I am planning to transition the display app from CRA to Vite to have a uniform dev tooling between the projects.

## How the Data is Stored

For storing configuration set by the admin, the server uses a package called NeDB. It provides a mongo-like API for interfacing with collections stored in files.
The server creates and uses two separate files for data, one to hold application settings `settings.db` and one to hold the application users `users.db`.

## How the Data is Retrieved

Every 5 seconds, the server makes the API request to get the events. Every second, the clients make a request to the server to get the latest events.
I chose this approach of relaying the data so that the school webpage's server wasn't overloaded by an API request from every client. Kind of the same way
you wouldn't give clients your API key and have them make requests on your behalf.

## Pictures
Picture of the main display that is shown on the TVs.
![Picture of the display](https://github.com/larryr1/larryr1.github.io/blob/main/projects/scpa-event/scpa-event-main.png?raw=true)

Picture of the admin interface on the Messages configuration tab.
![Pictures of the admin interface](https://github.com/larryr1/larryr1.github.io/blob/main/projects/scpa-event/scpa-event-messages.png?raw=true)

Video demo of the display and interface
[scpa-event Demo Video](https://larryr1.github.io/projects/scpa-event/scpa-event-demo.mp4)
