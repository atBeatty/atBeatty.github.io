---
layout: post
title:      "Attempting to { connect }"
date:       2021-01-17 21:48:26 -0500
permalink:  attempting_to_connect
---


My cohort started learning React and Redux over the Flatiron winter break. I mention this because this part of the curriculum got away from me when we returned to lectures. We jumped right into Redux,  and the concepts I tried to nail down in the React lessons became abstracted away with Redux functionality.  Nearing the end of the project, I started digging on my own to find documentation and examples on the web to help me layout the _app design structure_. 

The setup of my project is quite simple in its current state. The _LML Production App_ is an app that allows an agent/user create a production and keep track of all its properties. The current UX flow is as follows:


1. Add production
1. Navigate to the show page
1. Add a crew and its associated crew members


I have plans to extend the functionality by migrating additional tables into the back-end. The next phase of the build will be to incorporate an invoice table that _belongs_to_ a production. It's worth noting that my model, for the moment, is strong due to its top level _truth holder_. This is something I will take with me as a developer moving forward. 

> An easy model enables successful and clean code.

In my back-end, I tweaked the _:json return_ so that the production index returns all of the included relationships. I'm not sure if this is an efficient setup for the server, but it allowed me as a developer to return a wealth of information and data. 

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

Aside from this edit, the back-end was built using _rails scaffold_. It is a dynamic and straight-forward model. As mentioned above, I plan on incorporating a migration that introduces an  _INVOICE_ table, that will _belongTo_ perhaps an item/expense item table. This will have granular data associated with each expense.

When it came time to build out the components I regret not incorporating more flexibility in my file tree. Specifically, I should have minimally created 

```
-src
    -components
        -production
        -crew
```

Nevertheless, I was able to create a connection to my backend with a basic fetch and have the response render via React components. The difficult phase in this project was managing the peskiness of the store. I experimented for hours placing different dispatches of various types in various components. This was, in the end, one of the main reasons I picked up on some of the nuances of React, reacting with Redux.

My problem was that I was unaware of the following premise, of which I read during my time reviewing for the scheduled assessment.

> **...passing information between children components is taboo in React.**

As I fixed the problem, I learned quite a lot on how <Components> communicate with store concomitantly with the back-end database. Going into the project, I was stubborn and would not allow myself to separate the two entities. The code which led me to extend the app and its functionality properly was amending a <productionReducer> to my combineReducers method. Before I was delegating too much responsibility to the sole <productionsReducer>, that when I started testing all the ins and outs of the <Production Show Page> the dependencies on the one redux store introduced a handful of problems. 

The result is that you'll notice the two container files are very similar (as they should be). In earlier commits, the *production.js* file had significantly extra code to get what it needed to render. Even then, a refresh of any kind would throw errors.

TAKEAWAY: Be open to **Separation of Responsibilities/Concerns**


