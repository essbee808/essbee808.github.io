---
layout: post
title:      "JavaScript Project"
date:       2022-07-07 20:57:55 +0000
permalink:  javascript_project
---

Out of curiosity, I went for a drive after work and stopped by a driving range. To my surprise, I actually enjoyed it (My knees also thanked me after many years of playing basketball). I took this new hobby of mine, incorporated my research into my JavaScript + Rails project, and created CaliGolf. CaliGolf is a single page application (SPA) was designed for golf enthusiasts/hobbyists who are looking for local courses in California.

The requirements for the phase 4 project were as follows:

* The application must be an HTML, CSS, and JavaScript frontend with a Rails API backend. All interactions between the client and the server must be handled asynchronously (AJAX) and use JSON as the communication format.
* The JavaScript application must use Object Oriented JavaScript (classes) to encapsulate related data and behavior.
* The domain model served by the Rails backend must include a resource with at least one has-many relationship.
* The backend and frontend must collaborate to demonstrate Client-Server Communication. Your application should have at least 3 AJAX calls, covering at least 2 of Create, Read, Update, and Delete (CRUD).
* The client-side JavaScript code must use fetch with the appropriate HTTP verb and the Rails API should use RESTful conventions.

*Whew. *

I felt overwhelmed after initially reading through the project instructions. I created a to-do list to break down my tasks into smaller chunks then gathered some resources, including [a demo video](https://www.youtube.com/watch?v=6ukMsUkTRko), a fun [read](https://www.amazon.com/JavaScript-Kids-Playful-Introduction-Programming/dp/1593274084), and another [text for reference](https://www.amazon.com/JavaScript-Definitive-Most-Used-Programming-Language/dp/1491952024/ref=sr_1_1?crid=1T8CAY7JVY3JO&keywords=javascript+the+definitive+guide&qid=1657212415&s=books&sprefix=javascript+%2Cstripbooks%2C133&sr=1-1). 

In the frontend, I separated my logic into classes:
* course.js 
* courseService.js // handle fetch requests
* destination.js
* destinationService.js // handle fetch requests

For example...
```
class Course {

    static all = []
    static coursesContainer = document.getElementById("courses-container")
    static courseForm = document.getElementById("course-form-container")
    static coursesList = document.getElementById("courses-list")

    constructor({id, name, address, description, website, destination_id}){
       
        this.id = id
        this.name = name
        this.address = address
        this.description = description
        this.website = website
        this.destination_id = destination_id
        
        this.element = document.createElement('li')
        this.element.dataset.id = this.id 
        this.element.id = `course-${this.id}`
        this.element.addEventListener('click', this.handleDelete)
        Course.all.push(this)
    }
```

This project was the most challenging for me thus far, especially since I had to shift gears from Ruby to JavaScript. After many debugging sessions, conversations with my rubber duck, and practice projects, the app is working as intended. In the future I'd like to add additional features, including a map view of the golf course location and a comment section for each course. 
