---
layout: post
title:      "Sinatra Portfolio Project - Ez Rsvp"
date:       2019-08-30 06:56:55 +0000
permalink:  sinatra_portfolio_project_-_ez_rsvp
---


In recent months, I have taken on an additional role at work as an event planner for our monthly social outings. Planning activities for a non-profit organization is fun, however, it can also be overwhelming at times. There are other factors to consider when working with adults with intellectual and developmental disabilities, including dietary considerations, physical limitations, and modes of transportation (i.e. bus, rideshare, Access, etc.). As a way to encourage participation in the planning process, I wanted to create an application that allows both staff and clients to post, view, and rsvp for events. 

For my Sinatra project, I created "Ez Rsvp," a simple content management system for organizers and attendees. This app allows users to:
* create an account
* autenticate the user's information by email and password
* login / logout
* create new events
* view all events, including those submitted by other users
* edit and delete events that were created by the current user

The app is structured using the Model-View-Controller (MVC) framework. This created a separation of concerns, essentially "chunking" files based on their functionality. The three models include: User, Event, Rsvp. Views is further separated into three folders (i.e. users, events, rsvps) and consists of .erb files (HTML + embedded Ruby). Controllers act as the "middle man" that communicate information from the browser to the application and vice versa. 

I incorporated RESTful Routes to map between HTTP verbs and controller CRUD (Create, Read, Update, Delete) actions via Active Record. Each submitted event can only be modified if the current user is the creator of the event. With the added navigation menu at the top, it makes it easier for users to quickly locate show pages for events they created and those that they rsvp'd for. While refactoring, I decided to include a description text box in the left column. I went back to the terminal, created a new migration, and added a column titled "description" to my events table. DB Browser for SQLite was useful as it provided a visual representation of each of my tables. Even though it wasn't listed as one of the requirements, I wanted to expand my knowledge of CSS and added styling. 

Overall, I learned a great deal throughout the process and am proud of the outcome. In addition to displaying validation failures with error messages, I also included other info on the event show page (i.e. total number of attendees for an event, name of the event creator). 
