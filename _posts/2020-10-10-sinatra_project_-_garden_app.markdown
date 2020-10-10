---
layout: post
title:      "Sinatra Project - Garden App"
date:       2020-10-10 20:04:28 +0000
permalink:  sinatra_project_-_garden_app
---


My Sinatra Project is an application for homeowners and apartment renters who want to keep track of their many household plants. The MVP is defined with the help of the following user stories:

* Users can add a plant to their "My Greenhouse" seciton
* Users can view a stream of all of the plants in the app database, which has user information and plant care information
* Users can edit information of their own plants
* Users can delete plants from their own plants

I chose this subject of gardening because the structure of the UX provided a simple framework. It suits the User has many of relationship, which allowed me to really work with the logic without getting unnecessarily frustrated with erroneous and superfluous functionality. 

After developing the necessary framework, the idea grew on me and I had an easy time visualizing long term how the app would take shape. I could see comments and social interaction of all users and their nuanced experiences when it comes to  caring for house plants. 

In programming this app, I researched common house plants and extracted common care factors. These care factors became the fields for the Plant database. The second table of data in my database is the User table, which stores personal collections of plants by hooking into the following relationship:

A USER HAS MANY PLANTS.

Initially, I programmed the app so the user would have to take time to put in the Plant specs, which poses a problem. The problem is that it is tedious to enter the information pertaining to a specific plant, specifically, the scientific naming of most of the plant species.

As a result, the last programming and functionality that was added to the app was loading drop down lists and option buttons as opposed to text area boxes for putting in plant specs.

