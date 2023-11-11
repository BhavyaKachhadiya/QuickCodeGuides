---
title: Express
date: 2023-02-26 15:23:31
background: bg-[#edc545]
tags:
  - config
  - format
categories:
  - Backend
intro: |
  A quick reference cheatsheet for Express, a flexible and streamlined web framework for Node.js
plugins:
    - copyCode
---
## Recommend
### Recommend
```markdown {.wrap}
To start the server without re-executing the script, use the following command
```
#### Install Nodemon
```
npm i nodemon -g
```
#### To Run Nodemon
```
npx nodemon ./{YOUR_FILE_NAME}.js
```
### Express Generator
```markdown
npm i express-generator -g
```
```markdown
express {YOUR_APP_NAME} --view=ejs
```
```markdown
cd {YOUR_APP_NAME}
```
```markdown
npm i
```
## Basic of Express
### Hello World
```js
const express = require('express')
const app = express()

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(3000)
```

### Middleware
```js
const express = require('express');
const app = express();

app.use(function(req,res,next){
    console.log("Hello From Middleware");
    next();
})

app.get('/', (req, res) => {
  res.send('Hello World!');
})

app.listen(3000);
```

### Routes parameters
```js
const express = require('express');
const app = express();

app.get("profile/:username", function(req, res){
    res.send(`Hello from ${req.params.username}`);
})
app.get('/', (req, res) => {
  res.send('Hello World!');
})

app.listen(3000);
```
### Rendering EJS 
```js
const express = require('express');
const app = express();

app.set("view engine", "ejs");

app.get('/', (req, res) => {
  res.render("index");
})

app.listen(3000);
```
### Error Handing
```js
const express = require('express')
const app = express()

app.get("/errors", function(req, res,next){
    throw Error("Something went wrong")
});
app.get('/', (req, res) => {
  res.send('Hello World!')
})
app.use(function errorHandler(err,req, res,next) {
    if (res.headersSent){
        return next(err)
    }
    res.status(500)
    res.render('error', {err:err})
})
app.listen(3000)
```
