---
title: JavaScript
date: 2020-12-24 17:12:25
background: bg-[#ebd94e]
tags:
    - js
    - web
categories:
  - Frontend
intro: |
    A JavaScript cheat sheet with the most important concepts, functions, methods, and more. A complete quick reference for beginners.
plugins:
    - copyCode
---
## Basic
### Hoisting 

```js
console.log(a) //Output:undefined
var a = 12;
```
We can use variable before declaration
### primitives and reference 
``` {.wrap}
primitives=  number,null,string,undefined,boolean,etc
reference = {} [] ()
```
### if else  {.row-span-2}
```js
if (time < 10) {
  greeting = "Good morning";
} else if (time < 20) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}

// One Question

if(-1)
{
    console.log("True")
}
else
{
    console.log("False");
}
```
### Function
```js
function printHello()
{
    console.log("Hello World");
}
printHello();
```
#### Output
```markdown
Hello World
```
### Function with Argument
```js
function add(a,b)
{
  console.log(a+b);
}
add(2,8); 
```
#### Output
```markdown
10
```
## Arrow Functions
### fat arrow function
```js 
var ArrowFunction = ()=>{};
```

### fat arrow with one parameter 
```js {.wrap}
var arrowOneParameter = (parm)=>{console.log(parm)};
```
### fat arrow with implicit return
```
var ArrowImpicit = ()=>10;
```
## Loops
### for loop
```js
for(var i =0;i<=10;i++)
{
  console.log(i);
}

```
#### Output
```markdown
 1 2 3 4 5 6 7 8 9 10
```
### while loop
```js
var i = 1;
while (i <= 10) {
  text += "The number is :: " + i;
  i++;
}
```
#### Output
```markdown
 1 2 3 4 5 6 7 8 9 10
```
### For Each loop
```js
var a = [1,2,3,4,5,6,7,8,9,10];

a.forEach(function(val){
    console.log(val)
})
```
#### Output
```markdown
 1 2 3 4 5 6 7 8 9 10
```
### For In loop
```js
var obj ={
  name:"Bhavya",
  age: 17
}

for(var key in obj)
{
    console.log(key,obj[key]);
}

```
#### Output
```markdown
name Bhavya
age 17
```
## Array

### Array Declation 
```js
var array = [1,2,3,4,5,6,7,8.9,10];
```

### Array Basic Operations {.col-span-2 .row-span-2}
```js
var arr = [1,2,3,4,5,6,7,8,9];
 ```
#### To Add Values at Start
```js
arr.push(10);
//a = [1,2,3,4,5,6,7,8,9,10];
```
#### To Delete Values from last array
```js
arr.pop(); 
//a = [1,2,3,4,5,6,7,8,9];
```
#### To add Values at Start
```js
arr.unshift(0);
//a = [0,1,2,3,4,5,6,7,8,9];
```
#### To Delete Values from Start
```js
arr.shift(); 
//a = [1,2,3,4,5,6,7,8,9];
```
### Array Splice
```js
var arr = [1,2,3,4,5,6,7];
arr.splice(2,1);
```

#### Output
```markdown
arr=[1,2,4,5,6,7]
```
## Array Method
### groupBy 
```js {.wrap}
const people = [
{"name":"Michael","age":29},
{"name":"Andy", "age":30},
{"name":"Andy", "age":20},
{"name":"Justin", "age":19}
]

const peopleName = Object.groupBy(people, people => people.name);
console.log(peopleName);
```
#### Output
```js
{
    "Michael": [
        {
            "name": "Michael",
            "age": 29
        }
    ],
    "Andy": [
        {
            "name": "Andy",
            "age": 30
        },
        {
            "name": "Andy",
            "age": 20
        }
    ],
    "Justin": [
        {
            "name": "Justin",
            "age": 19
        }
    ]
}
```
### At
```js
const people = [
{"name":"Michael","age":29},
{"name":"Andy", "age":30},
{"name":"Andy", "age":20},
{"name":"Justin", "age":19}
]

const At = people.at(-1)
console.log(At);
```
#### Output
```js
{
    "name": "Justin",
    "age": 19
}
```

### Fill
```js
const people = [
{"name":"Michael","age":29},
{"name":"Andy", "age":30},
{"name":"Andy", "age":20},
{"name":"Justin", "age":19}
]

const At = people.fill(1)
console.log(At);
```
#### Output
```js
[1,1,1,1]
```

### toReversed
```js
const people = [
{"name":"Michael","age":29},
{"name":"Andy", "age":30},
{"name":"Andy", "age":20},
{"name":"Justin", "age":19}
]

const Reversed = people.toReversed();
console.log(Reversed);

```
#### Output for Reversed
```js
[
    {
        "name": "Justin",
        "age": 19
    },
    {
        "name": "Andy",
        "age": 20
    },
    {
        "name": "Andy",
        "age": 30
    },
    {
        "name": "Michael",
        "age": 29
    }
]
```
### toSpliced
```js
const people = [
{"name":"Michael","age":29},
{"name":"Andy", "age":30},
{"name":"Andy", "age":20},
{"name":"Justin", "age":19}
]

const Splice = people.toSpliced(1,1);
console.log(Splice);

```
#### Output for Spliced
```js
[
    {
        "name": "Michael",
        "age": 29
    },
    {
        "name": "Andy",
        "age": 20
    },
    {
        "name": "Justin",
        "age": 19
    }
]
```

### toSorted
#### Code for By Name
```js
const people = [
  { name: "Michael", age: 29 },
  { name: "Andy", age: 30 },
  { name: "Andy", age: 20 },
  { name: "Justin", age: 19 },
];

const sortedPeopleByName = people.sort((personA, personB) => {
  // Sort by name in ascending order
  if (personA.name < personB.name) {
    return -1;
  } else if (personA.name > personB.name) {
    return 1;
  } else {
    // If names are equal, sort by age
    return personA.age - personB.age;
  }
});

console.log(sortedPeopleByName);
```

#### Output for Sorted by Name
```js
[
    {
        "name": "Andy",
        "age": 20
    },
    {
        "name": "Andy",
        "age": 30
    },
    {
        "name": "Justin",
        "age": 19
    },
    {
        "name": "Michael",
        "age": 29
    }
]
```
#### Code for By Age
```js

const people = [
  { name: "Michael", age: 29 },
  { name: "Andy", age: 30 },
  { name: "Andy", age: 20 },
  { name: "Justin", age: 19 },
];

const sortedPeopleByAge = people.sort((personA, personB) => personA.age - personB.age);

console.log(sortedPeopleByAge);

```
#### Output for Sorted by Age 
```js
[
    {
        "name": "Justin",
        "age": 19
    },
    {
        "name": "Andy",
        "age": 20
    },
    {
        "name": "Michael",
        "age": 29
    },
    {
        "name": "Andy",
        "age": 30
    }
]
```
## Object
### Declation
```js {.wrap}
var a ={
    name:"Bhavya Kachhadiya", 
    //name=property
    email:"kachhadiyabhavya@gmail.com",
    //email=property
}

console.log(a.name);
console.log(a.email);
```
#### Output
```markdown
Bhavya Kachhadiya
kachhadiyabhavya@gmail.com
```
## Var VS Let
### Var
```js
function Var()
{
  for(var i = 1; i<10;i++)
  {
      console.log(i); //1 2 3 4 5 6 7 8 9 
  }
    console.log(i);//1 2 3 4 5 6 7 8 9 10
}
Var();
```
### Let
```js
function Let()
{
  for(let i = 1; i<10;i++)
  {
      console.log(i); //1 2 3 4 5 6 7 8 9 
  }
    console.log(i);//error :: i is not defined
}
Let();
```
### Difference 
```markdown {.wrap}
Difference between var and let
- var -> ES5
- let and const-> ES6
Var
- var is function scoped 
- we can use var inside parent function.
- var adds itself to the window object
Let
- Let is braces scoped
- we can use only inside braces.
- Let ,const dosen't adds itself to the window object
```
## Spread Operator
```js
var a = [1,2,3,4,5];
var b =[...a];

var obj = {name: "Bhavya"};
var copyobj = {...obj};
```
## Truthy and Falsy
### Falsy
```js
if(0)
{
    console.log("Truthy");
}
else
{
    console.log("Falsy");
}

// Output Falsy

if(NaN)
{
    console.log("Truthy");
}
else
{
    console.log("Falsy");
}
// Output Falsy
```
### Truthy
```js
if(-1)
{
    console.log("Truthy");
}
else
{
    console.log("Falsy");
}

//Output Truthy

if(10)
{
    console.log("Truthy");
}
else
{
    console.log("Falsy");
}

//Output Truthy
```

### Falsy and Truthy
```markdown
Falsy and Truthy

Falsy
Falsy values are
- 0
- false
- undefined
- null
- NaN
- document.all

Truthy
- other then Falsy
```

## Callback Function
### SetTimeout
```js
setTimeout(function(){
    consloe.log("2 second Completed");
},2000);
```
### First Class Function
```js
function abcd(a)
{
    a();
}
abcd(function(){
  console.log("This is a First Class");
})
```
### Object Deletetion
```js
var a = {
  name:"Bhavya",
  age:17
}

delete a.age;
//Output 
// a
// {name: 'Bhavya'}

delete a.name;
//Output 
// a
// {}
```
## higher-order function
### Method 1
```js
function abcd(val)
{

}
abcd(function(){})
```
### Method 2
```js
function abcd()
{
    return function(){}
}
```
### Exmaple
```js
var arr = [1,2,3,4,5];

arr.forEach(function(){}) 
```
#### What is Higher-Order function

 A higher-order function that accepts functions as parameters.

## Construtor
### Construtor Example {.col-span-3}
```js
function Car(make, model, year) {
  this.make = make;
  this.model = model;
  this.year = year;
}

// Creating instances of the Car object using the constructor
const car1 = new Car("Toyota", "Camry", 2020);
const car2 = new Car("Honda", "Civic", 2021);

console.log(car1); 
console.log(car2);
```
#### Output
```markdown
Car { make: 'Toyota', model: 'Camry', year: 2020 }
Car { make: 'Honda', model: 'Civic', year: 2021 }
```

## iife
### Example {.col-span-3}
iife -> immediately invoked function expression
```js
var ans = (function(){
    var privateVar= 10;
    
    return{
        getData: function(){
        console.log(privateVar);
      },
       setData: function(value)
      {
          privateVar = value;
      }
    };
  })();
```
#### Output
```markdown
ans.getData()
10

ans.setData(100)
ans.getData()
100
```
## Inhertinance
### Example
```js
var human = {
  canFly: false,
  canTalk: true,
  canWalk: true,
}
var programmer = {
    canProgram: true;
    canMakeAWebsite: true
}
programmer.__proto__= human;
```
#### Output
```markdown
 {canProgram: true, canMakeAWebsite: true}
   canMakeAWebsite: true
   canProgram:true
   [[Prototype]]: Object
     canFly:false
     canTalk:true
     canWalk:true
```
## This Keyword
```js
//global scope
console.log(this);

//function scope
 fuction abcd(){  
    console.log (this)
}

// method scope
var obj = {
    name: "Bhavya",
    method: function() {
        console.log(this);
    }
}
```
### this keyword Example
```js
var button = document.querySelector('button');

button.addEventListener("click",function(){
    console.log(this); // this === button
})
```
## Call, Blind, Apply
### Call
```js
function abcd(){
    console.log(this.age); // 17
}

var obj = {age: 17}

abcd.call(obj)

```
#### Output
```markdown
17
```
### Blind
```js
function abcd(){
    console.log(this.age); // 17
}

var obj = {age: 17}

var blindFunction = abcd.blind(obj)
blindFunction();
```
#### Output
```markdown
17
```
### Apply
```js {.wrap}
function abcd(val,val2){
    console.log(this.age,val,val2); // 17 1 2 3
}

var obj = {age: 17}

abcd.apply(obj,[1,2,3])
```
#### Output
```markdown
17 1 2 3
```
## Pure and Impure Function
### Pure Function 
```js
function abcd(a, b) {
    return a * b;
}
var ans1 = abcd(1, 2)
var ans2 = abcd(1, 2)
```
### Impure Function
```js
function abcd(val){
    return Math. random()*val;
}
var ans1 = (2)
var ans2 = (2)
```
## Promise
### Exmple
```js
var ans = new Promise((res,rej)=>{
    if (true) {
        return res();
    } else {
        return rej();
    }
})

ans
.then(function(){
    console.log("Done")
})
.catch(function(){
    console.log("Not Done")
})
```
### Async and await
```js {.wrap}
async function abcd()
{
    let raw = await fetch ("https://randomuser.me/api/")
    let ans = await raw.json();
    console.log(ans);
}

abcd();
```
## DOM

### Selection of an Element

```js
document.querySelector("h1") // Element
document.querySelector(".class") //Class
document.querySelector("#id") // ID
```
### Changing HTML and CSS
```js
var a = document.querySelector("h1")
a.innerHTML= "This is H1"

var a = document.querySelector("h1")
a.style.color = "red"
a.style.backgroundColor = "Black"
```
### Event Listener
```js
var a = document.querySelector("h1")
a.addEventListener("click", function(){
    console.log("clicked")
})
```

Refence
---------
- [Array Method](https://youtu.be/mSBnJvHtgD0?si=0Gd6CQfhPqAluJy2) _Web Dev Simplified_
- [Basic Javascript](https://www.youtube.com/watch?v=htznIeWKgg8&list=PLbtI3_MArDOkNtOan8BQkG6P8wf6pNVz-&index=3) _Sheryians Coding School_
- [Advance Javascript](https://www.youtube.com/watch?v=6kE8lrqfwHo&list=PLbtI3_MArDOkNtOan8BQkG6P8wf6pNVz-&index=15) _Sheryians Coding School_