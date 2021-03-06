# General Assembly WDI Project 4 : Full Stack Application

## Goal: To develop a full stack web application with a Python backend, SQL Database and React.js frontend.
### Timeframe
7 days

## Technologies used

* HTML5, JavaScript ES6
* React.js, Webpack, Babel, Axios, Yarn
* CSS3, CSS Animation, SCSS & Bulma
* Python, Flask, SQLAlchemy, Marshmallow, PostgreSQL, Pipenv
* Insomnia, Mocha, Chai & Enzyme
* Citymapper & Darksky APIs
* Git & GitHub
* Heroku

## Application - Bee Social

A hosted version of the application can be found here ----> [hidden-gems-2.herokuapp.com](https:/hidden-gems-2.herokuapp.com)

### Application overview
Bee Social is a platform where users can create and discover social events in their local area. The idea came from organising social activities and finding other people with the same interests, for example organising a five-a-side football game or running a book club.

The app was developed with React.js on the frontend and Python with a PostgreSQL database on the backend. External APIs were utilised to add additional functionality to the app. These included Citymapper to give indicative travel times to events and Darksky to give weather information for the date and location of events.

### Application Instructions
1. From the home page users can discover future 'Events' that have been posted on the platform. A search feature can be used to search by category or location.

![screenshot - Events Index](https://user-images.githubusercontent.com/39096986/54692788-77f21780-4b1d-11e9-8c52-9d3035824106.png)

2. The 'Event' show page, displays information regarding the event including other events from the organiser, number of attendees, location details with estimated journey time from the user's current location, and weather information for the date and location of the event. If a user is logged in they can attend this event by clicking the Attend button. Links for both Citymapper and Google Maps are displayed to give a more detailed journey options to the 'Event'.

![screenshot - Events Show](https://user-images.githubusercontent.com/39096986/54692638-38c3c680-4b1d-11e9-8c31-06b6b487c63a.png)

3. Users can browser and search for clubs of interest from the 'Club' Index page. Searches can be made based on category and location.

![Screenshot - Club Index](https://user-images.githubusercontent.com/39096986/54692484-02864700-4b1d-11e9-8435-dbe8b779a8d4.png)

4. The 'Club' show page displays information about the 'Club' including 'Club' members and future and past 'Events'. A user can follow the 'Club' by clicking the 'Follow' button. Once a follower of the 'Club' and chat facility is show on the page where discussion between members can take place.

![Screenshot - Club show page](https://user-images.githubusercontent.com/39096986/54692289-af13f900-4b1c-11e9-8e8b-b8536d7289a2.png)

![Screenshot - Club show page](https://user-images.githubusercontent.com/39096986/54694303-ef28ab00-4b1f-11e9-9605-7d41dc428557.png)

5. The user page displays future and past 'Events' the user is attending, 'Clubs' they following and 'Clubs'. A section of the user page displays 'Clubs' and 'Events' the created by the user, from these show pages 'Events' and 'Clubs' can be updated by the user.

![Screenshot - User page](https://user-images.githubusercontent.com/39096986/54692985-c9020b80-4b1d-11e9-9fe4-9a9a80ecd57e.png)

6. A logged in user can create 'Events' and 'Clubs' from the Organise tab in the navbar.

![Screenshot - Create Event](https://user-images.githubusercontent.com/39096986/54681591-aa434b00-4b04-11e9-93d1-c5eb7bf80dc4.png)

## Process

This project was delivered with one other developer. We managed the project with an agile methodology with a clear timeframe for us to deliver as much of the scope as possible. To assist this process we used a Kanban Board in the form of Trello to plan and manage our tasks, we also utilising daily stand-ups to track progress and understand blockers. Working in a group gave me further experience using Git workflows to manage the development of the project using branches for feature development.

The requirement to use an SQL Database meant we had to plan our database structure rigorously at the beginning of the project. Understand the relationship between data types was a key step, categories included many-to-many, one-to-many and one-to-one relationships. We designed the ERD for the application, which included primary database tables for User, 'Event' and 'Clubs'. A number of join tables were required for many-to-many relationships to allow attending and following functionality associated with 'Events' and 'Clubs' respectively.

Wireframes were produced to capture the layout of the application prior to any development taking place. This gave us a clear understanding of how each page would interact and a basic layout that we could apply consistently across the application.

Once our database structure and wireframes were confirmed the first step was to develop our backend functionality. Models and Controllers were created for 'Event', 'Club' and 'User'. For both 'Event' and 'Club' CRUD routes were created to allow users to manage 'Events' and 'Clubs' they have created. The User route focused on Register and Login to allow a user to have a profile where they could view and manage 'Events' or 'Clubs' they were attending or following.

The backend routes were tested using Insomnia to highlight bugs and to confirm the correct data was been returned or stored to the database.

The frontend of the application was built using React.js. I developed the 'Club' show page, user page, 'Club' and 'Event' Create and Edit pages. The application was styled using Bulma which was customised using Scss to inject consistent branding across the application.

A section of code I am proud of is the handle submit for the comments on the 'Club' show page. The handleMessageSubmit function made an AJAX request to the comments endpoint using the data saved to state from the comments input form. The AJAX response includes the 'Club' object with the updated comments which is stored to state to render the new comment in the comments display area. State data for the input field is then cleared to remove the new comment from the input box.

![Screenshot - Win screen](https://user-images.githubusercontent.com/39096986/54693390-7543f200-4b1e-11e9-8785-0b4aa1132504.png)

### Challenges
Working with SQL Database compared to NoSQL was a great experience but provided some challenges when using different data types. For example when using the time data type for the database to accept the data. This caused some issues on the front end as the built in time capture did not provide seconds by default. To overcome this problem I used a dropdown for hours and minutes on the frontend and stored these values as two separate integers in the database.

### Wins
Using the external APIs Citymapper and Darksky to display travel time and weather information for the event was a nice feature and a personal win for me. The AJAX request from the front end makes a single request to the backend containing the current users location and the id of the 'Event'. The backend them makes two AJAX requests, one to Darksky and one to Citymapper. The response from both is them processed to form a single response to the frontend. This was a really good exercise for me to become more familiar with external API documentation. By having a better understanding of the Darksky API I was able to refine my request to response with less data and making my API request more efficient.

![Screenshot - Win screen](https://user-images.githubusercontent.com/39096986/54695822-9575b000-4b22-11e9-9013-47cd25063dfc.png)

## Future features
1. Current 'Events' are only discoverable via the 'Events' index page of the app. To make discovery of events easier and more tailored to the user and feed could be added that displays the latest events that have been added by either 'Clubs' they follow or categories they are interested in.

2. Given more time to deliver the project more extensive testing on the frontend and testing of the backend API would have been carried out.
