---
title: MongoDB
date: 2023-04-05
background: bg-gradient-to-r from-green-900 via-green-600 to-green-400 hover:from-green-900 hover:via-green-700 hover:to-green-500
tags:
  - NoSQL
  - DB
categories:
  - Database
intro: The MongoDB cheat sheet provides you with the most commonly used MongoDB commands and queries for your reference. the cheatsheet is from mongodb developers website
plugins:
  - tooltip
  - copyCode
---

##  Setup Mongo
### Install Mongoose
```
npm i mongoose
```
## Connection {.cols-2}
### Connection 
```js

const mongoose = require("mongoose");

mongoose.connect("mongodb://127.0.0.1:27017/<DataBaseName>");
```
## Schema {.cols-2}
### Creating Schema
```js
const userschema = mongoose.Schema({
   username: String,
   name: String,
   age:Number
})

module.exports = mongoose.model("user",userschema);
```

## Crud

### Create
```js
const userModel = require("./user");
router.get("/create",async function(res,req){
 await userModel.create({
      username: "BhavyaKachhadiya",
      name: "Bhavya",
      age: 17
   });
})
```
### Delete

```js
const userModel = require("./user");
router.get("/delete",async function(res,req){
 await userModel.FindOneAndDelete({
      username: "BhavyaKachhadiya",
   });
})
```
### Find One User
```js {.wrap}
const userModel = require("./user");
router.get("/oneuser",async function(res,req){
 await userModel.findOne({username:"BhavyaKachhadiya"});
})
```
### Find all Users
```js {.wrap}
const userModel = require("./user");
router.get("/allusers",async function(res,req){
 await userModel.find();
})
```