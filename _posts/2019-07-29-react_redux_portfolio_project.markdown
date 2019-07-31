---
layout: post
title:      "React Redux Portfolio Project"
date:       2019-07-29 11:52:01 -0400
permalink:  react_redux_portfolio_project
---


The last part of the Flatiron School's course was to create an app using as much of what we have learned as possible. It was to use React and Redux,  ES6 syntax for its frontend and communicate with a Rails backend. I decided to create a simple shoe collection app to where you could view a collection of soccer shoes and add new shoes and like them. This project was a good test of my ability to create a complete app and apply everything i have learned. As i started creating my app, i had a better understanding of the flow of the code.

I started the project by working on the backend first and creating the database with postgresql incase i wanted to deploy the app to heroku in the future and the controller, routes and model. I installed the rack-cors gem to my gemfile to ensure there were no CORS issues when making requests from the client server.

To setup the app, i used the 'create-react-app' generator. This [article](https://www.fullstackreact.com/articles/how-to-get-create-react-app-to-work-with-your-rails-api/) does a good job of walking you through setting up a React app with Rails API. I have an internal API to store my shoe collection information. You can watch a short demo of the app here. 

Some of the features of the apps are: 

* You can add a new shoe to the collection 
* You can delete a shoe from the collection 
* You can like a shoe from the collection and view shoes that have the most likes 
* Uses a react-router and RESTful routing
* Uses Redux middleware to respond to and modify state changes
* Makes use of async actions to send data to and receive data from a server 

In ther frontend, everything is a component; either presentional or container. They are not different types of components, but instead, are a way of thinking on how to organize and simply a useful convention or programming pattern to use in a React app. 

I implemented Thunk as middleware to make action creators asynchronous. By using Thunk as my middleware i was able to return a function inside of my action creators instead of a JavaScript object; secondly that function would receive the store's dispatch function as its argument and allowing it to dispatch multiple actions from inside that returned function. This middleware gave the components the ability to access state and update, delete state data and send requests to the back-end. 

I can see how Redux is a great tool to use when creating apps. The Redux store allows us to hold the state in one JavaScript object and we can pass state to components as props. We update the state by passing both an action and the current state to our reducer and the reducer returns to us our new state. Remember, it returns a new state not change the previous state in store.

To change state, we create an action with a type key and pass the action as an arguent when we call the reducer which has a switch/case statement, which produces a new state.

By using the react-router, the app was able to navigate the app with RESTful routes.

The app in its current state checks off all the boxes required to complete the project. Next i would like to add a user login so that an individual user can save their favourite shoes to their personal collection. I would also like to add a search bar where a user can search and display shoes by their brands. 

For styling, i used the Semantic-Ui-React which is a easy to use framework for responsive layouts. 

By the end of the project i had a much better understanding of what's happening in a React app.

Check out my github to see the app and instructions to use it [here](https://github.com/amitnyc83/React-Redux-Rails-App)


