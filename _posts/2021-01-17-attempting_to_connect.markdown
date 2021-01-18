---
layout: post
title:      "Attempting to { connect }"
date:       2021-01-18 02:48:26 +0000
permalink:  attempting_to_connect
---


My cohort started learning React and Redux over the Flatiron winter break. I mention this because this part of the curriculum got away from me when we returned to lectures. We jumped right into Redux,  and the concepts I tried to nail down in the React lessons became abstracted away with Redux functionality.  Nearing the end of the project, I started digging on my own to find documentation and examples on the web to help me layout the _app design structure_. 

The setup of my project is quite simple in its current state. The _LML Production App_ is an app that allows an agent/user create a production and keep track of all its properties. The current UX flow is as follows:


1. Add production
1. Navigate to the show page
1. Add a crew and its associated crew members


I have plans to extend the funcitonality by migrating additional tables into the back-end. The next phase of the build will be to incorporate an invoice table that _belongs_to_ a production. It's worth noting that my model, for the moment, is strong due to its top level _truth holder_. This is something I will take with me as a developer moving forward. 

> An easy model enables succesful and clean code.

In my back-end, I tweaked the _:json return_ so that the production index returns all of the included relationships. I'm not sure if this is an efficient setup for the server, but it allowed me as a developer to return a wealth of informationa and data. 

```
{
"id": 4,
"name": "Pendleton Shoot",
"client": "Pendleton",
"crew_id": 5,
"created_at": "2021-01-17T22:48:24.399Z",
"updated_at": "2021-01-17T22:48:24.399Z",
"crew": {
"id": 5,
"rating": null,
"comments": null,
"created_at": "2021-01-17T22:48:24.392Z",
"updated_at": "2021-01-17T22:48:24.392Z"
},
"crew_members": [
{
"id": 11,
"name": "Ari Trames",
"email": "a@a.com",
"employer": "LML",
"rate": 38,
"crew_id": 5,
"created_at": "2021-01-17T22:49:43.047Z",
"updated_at": "2021-01-17T22:49:43.047Z",
"role": "PA"
}
]
}
```
