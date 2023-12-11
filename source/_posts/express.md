---
title: Express
date: 2023-02-26 15:23:31
background: bg-[#edc545]
tags:
  - Server 
categories:
  - Backend
intro: |
  A quick reference cheatsheet for Express, a flexible and streamlined web framework for Node.js
plugins:
    - copyCode
---
## Recommend
### Recommend

To start the server without re-executing the script, use the following command

#### Install Nodemon
```
npm i nodemon -g
```
#### To Run Nodemon
```
npx nodemon ./{YOUR_FILE_NAME}.js
```
### Express Generator
```
npm i express-generator -g
```
```
express {YOUR_APP_NAME} --view=ejs
```
```
cd {YOUR_APP_NAME}
```
```
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
```js {.wrap}
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
```js {.wrap}
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
## Sessions
### Session {.col-span-2}
#### Install Session
```
npm i express-session
```
#### Setup Session
```js {.wrap}
var session = require("express-session");

// app.set("view engine", "ejs");  after this line
app.use(session({
  resave:false,
  saveUninitialized:false,
  secret:"Anything"
}))
```
#### Create a new session
```js
router.get("/", function(req, res){
  req.session.name = "Bhavya";
});
```

#### Delete a session
```js
router.get("/deletesession", function(req, res){
  req.session.destroy(function(err){if(err){throw err}});
});
```

## Cookies
### Cookies
#### Create Cookies
```js
router.get("/", function(req, res){
  res.cookie("name","Bhavya");
});
```
#### Read Cookies
```js
router.get("/read", function(req, res){
  res.cookies.name;
});
```
#### Delete Cookies
```js
router.get("/read", function(req, res){
  res.clearCookies("name");
});
```

## Multer
### installtion
```markdown
npm i uuid multer
```
### any ejs file
```html
<form action="/upload" method="POST" enctype="multipart/form-data">
    <input type="file" name="file" id="file">
    <button type="submit">Upload</button>
</form>
```

### Multer.js
```js
const multer = require('multer');
const {v4: uuid4} = require('uuid');

const storage = multer.diskStorage({
  destination: function (req, file, cb) {
    cb(null, 'uploads/')
  },
  filename: function (req, file, cb) {
    const uniqueFileName = uuidv4();
    cb(null, uniqueFileName)
  }
});

const upload = multer({ storage: storage })
```
### Index.js
```js
const upload = require('./multerSetup');

router.post('upload', upload.single('file'),(req, res) =>{
  if(!req.file){
    return res.status(400).send('No file were uploaded.');
  }
  res.send('File uploaded successfully')
})
```
## authcode
### Code for Resgistering User
```js
const localStrategy = require("passport-loca");
passport.use(new localStrategy(userModel. authenticate()));

router.post('/register',function (req,res){
  var userdata = new userModel({
    username: req.body.username,
    secret: req.body.secret;
  });
  userModel.register(userdata,req.body.password).then(function (registereduser){
    passport.authenticate("local")(req,res,function(){
      res.redirect('/profile');
    })
  });
});
```

Reference
---
[Express](https://www.youtube.com/watch?v=pKJ4GGyDgJo&list=PLbtI3_MArDOk7J-8hR6CeB5U6bvgRKNNr&index=4) _Sheryians Coding School_