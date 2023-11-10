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
//what is hoisting?
//Ans: We can use variable before declaration
Example:
console.log(a) //Output:undefined
var a = 12;
```
### primitives and reference 
```
primitives=  number,null,string,undefined,boolean,etc
reference = {} [] ()
```
### if else 
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
```jsx
function printHello()
{
    console.log("Hello World");
}
printHello();
```
### Function with Argument
```jsx
function add(a,b)
{
  console.log(a+b);
}
add(2,8); // 10
```

## Loops
### for loop
```jsx
for(var i =0;i<=10;i++)
{
  console.log(i);
}
```
### while loop
```jsx
var i = 1;
while (i <= 10) {
  text += "The number is :: " + i;
  i++;
}
```
### For Each loop
```jsx
var a = [1,2,3,4,5,6,7,8,9,10];

a.forEach(function(val){
    console.log(val)
})
//Output 1 2 3 4 5 6 7 8 9 10
```
### For in loop
```jsx
var obj ={
  name:"Bhavya",
  age: 17
}

for(var key in obj)
{
    console.log(key,obj[key]);
}

//name Bhavya
//age 17
```
## Array

### Array Declation 
```jsx
var array = [1,2,3,4,5,6,7,8.9,10];
```

### Array Basic Operations
```jsx
var arr = [1,2,3,4,5,6,7,8,9];

arr.push(10); // To Add Values at Start
//a = [1,2,3,4,5,6,7,8,9,10];

arr.pop(); //To Delete Values from last array
//a = [1,2,3,4,5,6,7,8,9];

arr.unshift(0); // To add Values at Start
//a = [0,1,2,3,4,5,6,7,8,9];
arr.shift(); // To Delete Values from Start
//a = [1,2,3,4,5,6,7,8,9];
```
### Array Splice
```jsx
var arr = [1,2,3,4,5,6,7];
arr.splice(2,1);
//arr=[1,2,4,5,6,7]
```
## Object
### Declation
```jsx
var a ={
    name:"Bhavya Kachhadiya", //name=property
    email:"kachhadiyabhavya@gmail.com",//email=property
}

console.log(a.name); //Bhavya Kachhadiya
console.log(a.email);//kachhadiyabhavya@gmail.com
```
## Var VS Let
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

```markdown
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
## Sprid Opertor
```jsx
var a = [1,2,3,4,5];
var b =[...a];

var obj = {name: "Bhavya"};
var copyobj = {...obj};
```
## Truthy and Falsy
### Falsy
```jsx
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
```jsx
setTimeout(function(){
    consloe.log("2 second Completed");
},2000);
```
### First Class Function
```jsx
function abcd(a)
{
    a();
}
abcd(function(){
  console.log("This is a First Class");
})
```
### Object Deletetion
```jsx
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
### higher-order function
```jsx
//Method 1
function abcd(val)
{

}
abcd(function(){})

// Menthod 2
function abcd()
{
    return function(){}
}

//Exmaple

var arr = [1,2,3,4,5];

arr.forEach(function(){}) // here forEach is higherOrder Function

// A higher-order function that accepts functions as parameters.
```
## Construtor
### Construtor Expalme
```jsx
function Car(make, model, year) {
  this.make = make;
  this.model = model;
  this.year = year;
}

// Creating instances of the Car object using the constructor
const car1 = new Car("Toyota", "Camry", 2020);
const car2 = new Car("Honda", "Civic", 2021);

console.log(car1); // Outputs: Car { make: 'Toyota', model: 'Camry', year: 2020 }
console.log(car2); // Outputs: Car { make: 'Honda', model: 'Civic', year: 2021 }
```
## iife
```jsx
// iife -> immediately invoked function expression

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

//ans.getData()
//10

// ans.setData(100)
//ans.getData()
//100
```
## Inhertinance
```jsx
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
// Output
// {canProgram: true, canMakeAWebsite: true}
//   canMakeAWebsite: true
//   canProgram:true
//   [[Prototype]]: Object
//     canFly:false
//     canTalk:true
//     canWalk:true
```
## This Keyword
```jsx
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
### this keyword Exmplae
```jsx
var button = document.querySelector('button');

button.addEventListener("click",function(){
    console.log(this); // this === button
})
```
## Call, Blind, Apply
### Call
```js
// Call

function abcd(){
    console.log(this.age); // 17
}

var obj = {age: 17}

abcd.call(obj)
```
### Blind
```js
// Blind

function abcd(){
    console.log(this.age); // 17
}

var obj = {age: 17}

var blindFunction = abcd.blind(obj)
blindFunction();
```
### Apply
```js
// Apply
function abcd(val,val2){
    console.log(this.age,val,val2); // 17 1 2 3
}

var obj = {age: 17}

abcd.apply(obj,[1,2,3])
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
### Working of setTimeOut
```jsx
console.log("1")
setTimeout(function(){console.log("2")},2000)
console.log("3");
console.log("4");
console.log("5");

//Output
// 1
// 3
// 4
// 5
// 2
```
## Promise
### Exmple
```jsx
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
```jsx
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

```jsx
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