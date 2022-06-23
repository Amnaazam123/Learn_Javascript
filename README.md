# Learn Javascript
### Data Types :
Primitives - pass by value - (string, number, null, boolean, undefined, symbol)
Non-Primitives pass by reference - (functions, arrays and objects)
```
let length = 16;                               // Number
let num = 16.32                                // Number
let lastName = "Azam";                         // String
//Method 1
const cars = ["Saab", "Volvo", "BMW"];         // Arrays =>delete[1]=>[1]=undefinded
// Method 2
const secondArray = new Array(3);
secondArray[0] = "JavaScript";
secondArray[1] = "Python";
secondArray[2] = "Go";

let car;                                       // undefined
let x = {                                      // Object
          firstName:"Amna",
          lastName:"Azam"
        }; 

```
JavaScript evaluates expressions from left to right.
 ```
 let x = 16 + 4 + "Volvo";        //20Volvo
 let x = "Volvo" + 16 + 4;        //Volvo164
 ```
JavaScript has dynamic types.
```
let x;           // Now x is undefined
x = 5;           // Now x is a Number
x = "John";      // Now x is a String
```
### ES6 Javascript
JavaScript was invented by Brendan Eich in 1995, and became an ECMA standard in 1997.
ECMAScript is the official name of the language.
ECMAScript versions have been abbreviated to ES1, ES2, ES3, ES5, and ES6.
ECMAScript 2015 was the second major revision to JavaScript and is also known as ES6 and ECMAScript 6.
ES6 has some new features including :
<b>The let keyword</b>, 
<b>The const keyword</b>, 
<b>Arrow Functions</b>, 
<b>For/of</b>, 
<b>Map Objects</b>, 
<b>Set Objects</b>, 
<b>Classes</b>, 
<b>Promises</b>, 
<b>Symbol</b>, 
<b>Default Parameters</b>, 
<b>Function Rest Parameter</b>, 
<b>String.includes()</b>, 
<b>String.startsWith()</b>, 
<b>String.endsWith()</b>, 
<b>Array.from()</b>, 
<b>Array keys()</b>, 
<b>Array find()</b>, 
<b>Array findIndex()</b>, 
<b>New Math Methods</b>, 
<b>New Number Properties</b>, 
<b>New Number Methods</b>, 
<b>New Global Methods</b>, 
<b>Object entries</b>, 
<b>JavaScript Modules</b>

<h2>The let keyword</h2>
Let datatype has somehow same properties as C++ Datatypes.<br>
Let declaration is block scoped, and can not be redeclared in same scope. It can not be accessed before declaration.

```
let x = 10;        // Here x is 10
{
  let x = 20;
  // Here x is 20
}
// Here x is 10
```

<h2>The const keyword</h2>
Same properties as Let in javascript but its value cannot be reassigned. 

```
  const x=123;
  x = 345;                   //ERROR!!
  console.log(x)
```
<h2>The Var keyword</h2>
Var is global scoped and can be accessed before declaration.

```
var x = 10;        // Here x is 10
{
  var x = 20;
  // Here x is 20
}
// Here x is 20
```

# Regular Functions
```
function sum(a,b){
    return a+b;
}
console.log(sum(1,2))
```

# Anonymous Functions
```
var sum1 = function(a,b){
    return a+b;
}
console.log(sum1(1,3))
```

# Arrow Functions

```
var sum1 = (a,b) => a+b;
console.log(sum1(4,6))

var sum2 = () => 1 + 2;
console.log(sum2())

var average = (a,b)=>{
    let z = a+b
    z = z / 2
    return z
}
console.log(sum3(1,5))
```
Note : A regular function declaration defines a function that will be executed when it is invoked. A function expression is similar to a function declaration, with the difference that it can be stored in a variable. As soon as the function is defined with an expression, it is invoked. Later on it is just used.
### Name Function Expression (NFE)
```
var boo = function boo () {
  alert(1);
};
```
### Anonymous Function Expression (AFE)
```
var boo = function () {
  alert(1);
};
```
<h2>Arithmetic operators</h2>
+, -, *, /, **, %, ++, --

<h2>Assignment operators</h2>
=, +=, -=, *=, /=, **=, %=

<h2>Logical operators</h2>
&&, ||, !

<h2>Bitwise operators</h2>
&, |, ~, >>, <<, ^

<h2>Comparison operators</h2>
==, ===, <, >, <=, >=, !=, !==

<h2>Loops</h2>
- For Loop

```
let data = [10,20,30,40,50]
for(let i=0;i<5;i++){
    console.log(data[i])
}

let i = 0;
for (; i < 5; i++) {
    console.log(data[i])
}

let x = 0;
for (; x < 5; ) {
    console.log(data[x])
  x++;
}
```

- For in loop
```
for (let num in data)
{
    console.log(data[num])
}
```

- For of loop
```
for (let num of data)
{
    console.log(num)
}
```

- Foreach loop
```
data.forEach(num => {
    console.log(num);
});
```

- While loop
```
let i=0
while(i>5){
    console.log(data[i])
    i++
}
```

- Do while loop
```
let i=0
do{
    console.log(data[i])
    i++
}while(i>5)
```

# Objects
Almost everything in JavaScript is an object. In fact, only six things are not objects. They are — null , undefined , strings, numbers, boolean, and symbols.
```
let Person = {
    firstName:"Amna",
    lastName:"Azam",
    fullName:function(){
        console.log(this.firstName + " " + this.lastName)
    }
}

const p1= Person.firstName        //or
const p2 = Person["firstName"]

console.log(Person.lastName)      //or
console.log(Person["lastName"])

Person["fullName"]();             //or
Person.fullName() 
```

# this keyword
In a regular function, the "this" keyword represents different objects with which the function is called.<br>
In arrow function,  the "this" keyword represents object of that scope in which function is defined.

```
let f = function(){
console.log(this)
}

let f2 = () => {
    console.log(this)
}

f()                     //window/global object
f2()                    //{}
```

```
const Person={
    func:function(){
        console.log(this)        //{ func: [Function: func], func2: [Function: func2] }
    },
    func2:()=>{
        console.log(this)        //{}
    }
}


Person.func();
Person.func2();
```

```
class Person{
    func = () => {
        console.log(this)        //Person { func: [Function: func] }
    }
    func2(){
        console.log(this)        //Person { func: [Function: func] }
    }
};


let p = new Person();
p.func()
p.func2()
```

# Object Reference and Copying
Both message and phrase variables have individual memories. You change the value of message, phrase value do not get affected.
```
let message = "Hello!";
let phrase = message;
```
Objects have shared memories. You change the value of user name, admin name get affected.
```
let user = { name: "John" };
let admin = user;      //copy reference

console.log(user)      //{ name: 'John' }   
console.log(admin)     //{ name: 'John' }

user.name="Amna"

console.log(user)     //{ name: 'Amna' }
console.log(admin)    //{ name: 'Amna' }
```
```
let a = {name:"Amna"};
let b =  {name:"Amna"};          // copy the reference

console.log( a == b ); // false, both objects are totally independent
console.log( a === b ); // false
```
```
let a = {name:"Amna"};
let b = a;          // copy the reference

console.log( a == b ); // true, both variables reference the same object
console.log( a === b ); // true


```
# Constructor and new Operator
The constructor function is a regular JavaScript function that contains a recipe to create a new object. When we invoke it using the new operator it creates a new instance of the object and returns it.

```
function Person(firstName, lastName, age) {
  this.firstName = firstName;
  this.lastName = lastName;
  this.age = age;
  this.fullName = function() {
    return this.firstName + ' ' + this.lastName;
  };
}

let person = new Person('Alex', 'Ferguson', 50);
console.log(person.fullName());
```

# Currying
Currying takes a function that receives more than one parameter and breaks it into series of unary (one parameter) functions.
```
const buildSandwich = function(ingredient1){
    return function(ingredient2){
        return function(ingredient3){
            console.log(ingredient1,ingredient2,ingredient3)
        }
    }
}
buildSandwich("a")("b")("c")

//arrow notation
const build = ingredient1=> ingredient2 => ingredient3 => console.log(ingredient1,ingredient2,ingredient3)
build("a")("b")("c")
```

```
const multiply = (x,y) => x*y           //one function takes two parameters
const curriedMultiply = x => y => x*y   //two nested functions taking unary parameters

console.log(curriedMultiply(2))         //[Function (anonymous)]
console.log(curriedMultiply(2)(3))      //6  

const func = curriedMultiply(2)        //[Function (anonymous)]
console.log(func(3))                   //6
```
# Lexical scope
Nest child functions have access to their parent functions. If we have child function with in parent function, the child function has access to the scope of parent function, and has access to global scope. <br>
P.S. Lexical scope is not closure but an important part of closure. Here childFunction is closure to parentFunction. 
```
//global scope
let x =10
const parentFunction = () => {
    //local scope
    let y=100;
    console.log(x,y)
    const childFunction = () => {
        x++ 
        y++
        console.log(x,y)
    }
    childFunction()
}
parentFunction()
```
# Closure
A closure is a function having access to perent scope <b>EVEN AFTER THE PARENT FUNCTION HAS CLOSED.</b> A closure is created when you define a function, not when function is executed.
```
//global scope
let x =10
const parentFunction = () => {
    //local scope
    let y=100;
    console.log(x,y)           //10 100
    const childFunction = () => {
        x++ 
        y++
        console.log(x,y)
    }
    return childFunction
}
let childFunc = parentFunction()
childFunc()           //11 101
childFunc()           //12 102
childFunc()           //13 103
```
Immediately Invoked Function in closure:
```
//global scope
let x =10
const parentFunction = (() => {
    //local scope
    let y=100;
    console.log(x,y)           //10 100
    const childFunction = () => {
        x++ 
        y++
        console.log(x,y)
    }
    return childFunction
})()

parentFunction()           //11 101
parentFunction()           //12 102
parentFunction()           //13 103
```
# Hoisting
When javascript interpreter processes the script, it takes the function declarations, and variables declarations and moves them at the top of script, not physically but in memory.
Let and const are not hoisted.
```

//-------------------------------------------------------Error!
console.log(y)
const y = 3            //It must be intialized when declared


//---------------------------------------------------------Error!
z = 5
console.log(z)
let z = 5

//----------------------------------------------------------Okayy!
x = 5
console.log(x)
var x

//-------------------------------------------------------undefined!
console.log(x)     //initializations are not hoisted
var x = 5

//-----------------------------------------------------------okayy!
func()
function func() {
    console.log("Hello!")
}

//-----------------------------------------------------------Error!
//arrow functions are somehow initializations
func()
var func = () => {
    console.log("Hello!")
}

```
# Null and Undefined
undefined is a type, whereas null an object.
```
var demo;
alert(demo); //shows undefined
alert(typeof demo); //shows undefined
```
```
var demo = null;
alert(demo); //shows null
alert(typeof demo); //shows object
```
# Event Bubling and Event Capturing
Event Bubbling(current to outer) − Whenever an event happens on an element, the event handlers will first run on it and then on its parent and finally on the last parent. Event Capturing(current to inner) − It is the reverse of the event bubbling and here the event starts from the parent element and then to its child element.
- true - Capturing
- false - Bubbling (by default)
```
<html>
  <head></head>
  <body>
    <article id="ancestor" >
      article element
      <div id="parent" >
        div element
        <p id="child" >
          p element
        </p>
      </div>
    </article>
  </body>
</html>

<script>
  // Script to click event handler to capture on each element
  for(let elem of document.querySelectorAll('*')) {
    elem.addEventListener("click", e => console.log("Capturing:", elem.tagName), true);
  }
</script>
```
# why obj1 === obj2 returns False
when you say a==b or a===b, you're not comparing the objects, you're comparing the references in a and b to see if they refer to the same object. It return False when you have 2 distincts objects in memory.
```
let ob1={a:"b"}
let ob2={a:"b"}

console.log(ob1==ob2)       //false
console.log(ob1===ob2)      //false

let ob3 = ob2
console.log(ob2==ob3)       //true
console.log(ob2===ob3)      //true
```
# why var1 === var2 returns False
It returns false when you have different datatypes. Even if you have different values but same datatype, "===" must return false even with same data type.
```
let a=10
let b="10"

console.log(a===b)   //false
console.log(a==b)    //true

let c="11"
let d="10"

console.log(c===d)   //false
console.log(c==d)    //false

```
# Javascript Timing Events
 - setTimeout()
setTimeout(function, milliseconds) - Executes a function, after waiting a specified number of milliseconds.
```
function myFunction() {
    alert('Hello');
  }
<button onclick="myVar = setTimeout(myFunction, 3000)">Try it</button>
<button onclick="clearTimeout(myVar)">Stop it before 3s</button>
```
 - setInterval()
setInterval(function, milliseconds) - Same as setTimeout(), but repeats the execution of the function continuously.
```
function myFunction() {
    alert('Hello');
  }
<button onclick="myVar = setInterval(myFunction, 3000)">Try it</button>
<button onclick="clearInterval(myVar)">Stop it</button>
```
# Destructuring of arrays
Before E6
```
let User = ["Amna",20]
let name = User[0]
let age = User[1]
```
After E6, There is destructuring of arrays
```
let [name,age] = User
console.log(name)        //Amna
console.log(age)         //20

//if you only want to get age
let [,age] = User        //name=undefined,age=20

let myArr = ["Amna",20,"Okara","Arshia","Arooj"]
let [name,age,...rest] = myArr
console.log(name)         //Amna
console.log(age)          //20
console.log(rest)         //["Okara","Arshia","Arooj"]
```

# Destructuring of objects
Before E6
```
let User = {
    name:"Amna",
    age:20,
    city:"okara",
    phone:123456789,
    rollNo:"BSEF19M009"
}

let name = User["name"]
let age = User["age"]
let city = User["city"]
```
After E6, There is destructuring of objects
```
//These names must match with dictionary keys otherwise undefined.
let {name,age,city} = User
console.log(name,age,city)        //Amna 20 okara


//if you only want to get age and city
let {age,city} = User        //or let {age:A,city:C} = User; console.log(A,C)  
console.log(age,city)        //20 okara


let {name,age,...rest} = User
console.log(name)         //Amna
console.log(age)          //20
console.log(rest)         //{ city: 'okara', phone: 123456789, rollNo: 'BSEF19M009' }
```
# 4 Ways to Copy Objects in JavaScript
- Use the spread (...) syntax
- Use the Object.assign() method
- Use the JSON.stringify() and JSON.parse() methods
- Direct Assignment<br>
Both spread (...) and Object.assign() perform a shallow copy while the JSON methods and direct Assignment(copy) carry a deep copy.A deep copying means that value of the new variable is disconnected from the original variable while a shallow copy(2 memories) means that some values are still connected to the original variable.

```
const person = {
    firstName: 'Amna',
    lastName: 'Azam'
};


// using spread ...
let p1 = {...person};

// using  Object.assign() method
let p2 = Object.assign({}, person);

// using JSON
let p3 = JSON.parse(JSON.stringify(person));

```

# Function Objects
Functions are objects.
- Lets assign property to function just like objects.
```
// Function declaration.
function showFavoriteIceCream() {
  const favIceCream = 'chocolate';
  console.log(`My favorite ice cream is ${favIceCream}`);
}

// Let's assign a property.
showFavoriteIceCream.flavours = ['chocolate', 'vanilla', 'strawberry'];
console.log(showFavoriteIceCream);          // { [Function: showFavoriteIceCream] flavours: [ 'chocolate', 'vanilla', 'strawberry' ] }
```
- Let's assign a function to function just like objects.
```
// Function declaration.
function showFavoriteIceCream() {
  const favIceCream = 'chocolate';
  console.log(`My favorite ice cream is ${favIceCream}`);
}

// Let's assign a property.
showFavoriteIceCream.flavours = ['chocolate', 'vanilla', 'strawberry'];

// Let's assign a function.
showFavoriteIceCream.showFlavours = function () {
  return this.flavours;
};

console.log(showFavoriteIceCream);           //{ [Function: showFavoriteIceCream] flavours: [ 'chocolate', 'vanilla', 'strawberry' ], showFlavours: [Function] }
```
# Prototype
JavaScript is a dynamic language. You can attach new properties to an object at any time as shown below.
```
function Student() {
    this.name = 'John';
    this.gender = 'Male';
}

var studObj1 = new Student();
studObj1.age = 15;
alert(studObj1.age); // 15

var studObj2 = new Student();
alert(studObj2.age); // undefined
```
As you can see in the above example, age property is attached to studObj1 instance. However, studObj2 instance will not have age property because it is defined only on studObj1 instance.<br>
So what to do if we want to add new properties at later stage to a function which will be shared across all the instances?<br>
The prototype is an object that is associated with every functions and objects by default in JavaScript, where function's prototype property is accessible and modifiable and object's prototype property (aka attribute) is not visible.
```
//constructor function
function Student() {
    this.name = 'John';
    this.gender = 'M';
}
//adding attribute to constructor method 
Student.prototype.age = 15;
// adding a method to the constructor function
Student.prototype.greet = function() {
    console.log('hello' + ' ' +  this.name);
}

var studObj1 = new Student();
console.log(studObj1.age);    // 15

var studObj2 = new Student();
console.log(studObj2.age);  // 15

studObj1.age = 20
console.log(studObj1.age);     // 20
console.log(studObj2.age);     // 15


Student.prototype.age = 20;

console.log(studObj1.age); // 20
console.log(studObj2.age); // 25

console.log(Student.prototype)      //{ age: 20, greet: [Function (anonymous)] }
```

# Promise
"Producing code" is code that can take some time<br>
"Consuming code" is code that must wait for the result<br>
A Promise is a JavaScript object that links producing code and consuming code<br>
The function passed to new Promise is called the executor. <br>
The promise object returned by the new Promise constructor has 2 internal properties:
- state — initially "pending", then changes to either "fulfilled" when resolve is called or "rejected" when reject is called.
- result — initially undefined, then changes to value when resolve(value) called or error when reject(error) is called.
```
let promise = new Promise(function(resolve, reject) {
  // the function is executed automatically when the promise is constructed

  // after 1 second signal that the job is done with the result "done"
  setTimeout(() => resolve("done"), 1000);
});
```
We can see two things by running the code above:
- The executor is called automatically and immediately (by new Promise).
- The executor receives two arguments: resolve and reject. These functions are pre-defined by the JavaScript engine, so we don’t need to create them. We should only call one of them when ready.
- After one second of “processing” the executor calls resolve("done") to produce the result. This changes the state of the promise object from pending to fulfilled.
```
let promise = new Promise(function(resolve, reject) {
  // after 1 second signal that the job is finished with an error
  setTimeout(() => reject(new Error("Whoops!")), 1000);
});
```
A Promise object serves as a link between the executor (the “producing code” or “singer”) and the consuming functions (the “fans”), which will receive the result or error.
```
promise.then(
  function(result) { /* handle a successful result */ },
  function(error) { /* handle an error */ }
);
```
- The first argument of .then is a function that runs when the promise is resolved, and receives the result.
- The second argument of .then is a function that runs when the promise is rejected, and receives the error.

# Error Handling
- The try statement defines a code block to run 
- The catch statement defines a code block to handle any error.(JavaScript will actually create an Error object with two properties: name and message.)
- The finally statement defines a code block to run regardless of the result.
- The throw statement defines a custom error which is used in try block.
- try alone cannot be used. you must use catch or hinally with it.
### try-catch
```
try {
    lert("Welcome guest!");                       //typo mistake, *alert
  }
catch(error) {
    console.log("There is an error!!", error.message)           //There is an error!! lert is not defined
}
```
### throw
```
try{
    let x=5
    if(x==5){throw "wrong value"}
}
catch(error){
    console.log(error)          //wrong value
}
```
### finally
```
try{
    let x=5
    if(x==5)
    {
       throw "wrong value"
    }
}
catch(error){
    console.log(error)          //wrong value
}
finally{
    console.log("I do not care")     //I do not care
    }
```
# Pure Function
A Pure Function is a function (a block of code) that always returns the same result if the same arguments are passed. Rather, it only depends on its input arguments.
- Pure function example:
```
function calculateGST( productPrice ) {
    return productPrice * 0.05;
}
```
- Not Pure Function Example 
```
var tax = 20;
function calculateGST( productPrice ) {
    return productPrice * (tax / 100) + productPrice;
}
```
# Geberators
A generator can pause midway and then continues from where it paused. The asterisk denotes that the generate() is a generator, not a normal function. The yield statement returns a value and pauses the execution of the function. A generator returns a Generator object without executing its body when it is invoked. It has two properties : value and done.  It has next() method to resume the function execution.
```
function * myGenerator(){
  yield 1
  yield 2
  yield 3
}

console.log(myGenerator())      //Object [Generator] {}
let g = myGenerator()           
console.log(g.next())           //{ value: 1, done: false } 
let g2 = g.next()   
console.log(g2)                 // { value: 2, done: false }             
console.log(g2.value)           // 2
console.log(g.next())           //{ value: 3, done: false } 
console.log(g.next())           //{ value: undefined, done: true } 

//ID GENERATOR
function * myGenerator(){
  let id=1
  while(true){
    yield id
    id++
  }
}

console.log(myGenerator())      //Object [Generator] {}
let g = myGenerator()           
console.log(g.next())           //{ value: 1, done: false } 
console.log(g.next())           //{ value: 2, done: false } 
console.log(g.next())           //{ value: 3, done: false } 
console.log(g.next())           //{ value: 4, done: false } 


```
# Js Modules
JavaScript modules allow you to break up your code into separate files.
This makes it easier to maintain the code-base.
JavaScript modules rely on the import and export statements.
### Export
Let us create a file named message.js, and fill it with the things we want to export in other file. There are two ways to export<br>
Default and Named Export: You can only have one default export in a file.
```
const message = () => {

};
const message1 = () => {

};
const message2 = () => {
  
};
export default message;
export {message1,message2}

//-------------------------------------- OR
//default export
export default function message(){

};

//named export
export const message1 = () => {

};
export const message2 = () => {

};
  
```
### import
You can import modules into a file in two ways, based on if they are named exports or default exports.<br>
```
//named import
import { message1 as msg, message2 } from "./message.js";
console.log(msg())
console.log(message2())

//default import
import message from "./message.js";
```
# Function chaining
### Before chaining
```
var makeObj = function(){
  this.i = 0;

  this.increment = function(){
    this.i = this.i + 5
  }

  this.decrement = function (){
    this.i = this.i - 1
  }

  this.print = function (){
    console.log(this.i)
  }
}
var obj = new makeObj()
obj.increment()
obj.decrement()
obj.print()          //4
```
### After method chaining
```
var makeObj = function(){
  this.i = 0;

  this.increment = function(){
    this.i = this.i + 5
    return this
  }

  this.decrement = function (){
    this.i = this.i - 1
    return this
  }

  this.print = function (){
    console.log(this.i)
  }
}
var obj = new makeObj()
obj.increment().decrement().print()           //4
```
# Concurrency Model and Event Loop
The event loop simply checks the call stack, and if it is empty (which means there are no functions in the stack) it takes the oldest callback from the callback queue and pushes it into the call stack which eventually executes the callback.
```
console.log('hi');

setTimeout(function() {
     console.log('Amna')
},5000);

console.log('JS')
```
### Code Explaination:
Message hi is pushed in stack, exectued and then poped. setTimeout is web API, This function is given to browser to excute. During this 5s period, Message JS is pushed in stack, exectued and then poped. After 5s, Browser pushes this function to callback queue. Here event loop check if stack is empty, then this function from queue is pushed to stack. Message "Amna" is pushed to stack, executed and poped. Finally this function poped from stack and program ends.

# walking in DOM 
```
<html>

<head>
  <script>
    alert( "From HEAD: " + document.body ); // null, there's no <body> yet
  </script>
</head>

<body>

  <script>
    alert( "From BODY: " + document.body ); // HTMLBodyElement, now it exists
  </script>

</body>
</html>
```
```
<html>
<body>
  <div>Begin</div>

  <ul>
    <li>Information</li>
  </ul>

  <div>End</div>

  <script>
    for (let i = 0; i < document.body.childNodes.length; i++) {
      alert( document.body.childNodes[i] ); // Text, DIV, Text, UL, Text, DIV, Text, SCRIPT
    }
  </script>
  ...more stuff...
</body>
</html>
```
```
<html>
<body>
  <div>Begin</div>

  <ul>
    <li>Information</li>
  </ul>

  <div>End</div>

  <script>
    for (let elem of document.body.children) {
      alert(elem); // DIV, UL, DIV, SCRIPT
    }
  </script>
  ...
</body>
</html>
```

```
// parent of <body> is <html>
alert( document.body.parentNode === document.documentElement ); // true

// after <head> goes <body>
alert( document.head.nextSibling ); // HTMLBodyElement

// before <body> goes <head>
alert( document.body.previousSibling ); // HTMLHeadElement
```
```
<table id="table">
  <tr>
    <td>one</td><td>two</td>
  </tr>
  <tr>
    <td>three</td><td>four</td>
  </tr>
</table>

<script>
  // get td from first row, second column.
  let td = table.rows[0].cells[1];
  td.style.backgroundColor = "red"; // highlight it
</script>
```
![image](https://user-images.githubusercontent.com/71166016/175239886-85ceb2bd-b062-415e-a23c-18cfd9d193fe.png)

# 🤩🤩🤩🤩 Some Problems 🤩🤩🤩🤩
### Problem - 1
- Arrays are passed by reference.
```
var arr1 = "john".split('')     //['j','o','h','n']
var arr2 = arr1.reverse()       //['n','h','o','j'] - reverse of arr1 is copied by reference in arr2

var arr3 = "jones".split('')     //['j','o','n','e','s']
                
arr2.push(arr3)                  //['n','h','o','j',['j','o','n','e','s']]

console.log(arr1.length())       //5
console.log(arr1.slice(-1))      //j,o,n,e,s

console.log(arr2.length())       //5
console.log(arr2.slice(-1))      //j,o,n,e,s
```

### Problem - 2
- When Function returns object.
```
function foo1(){
    return {
        bar:"hello"
    };
}
function foo2(){
    return {
        bar:"hello"
    };
}
console.log(foo1().bar)      //hello
console.log(foo2().bar)      //hello
```

### Problem - 3
- Immediately invoked function and currying
```
let func = ((x)=>{
    return((y)=>{
        console.log(x)     //2
    })(1)
})(2)
```
### Problem - 4
- Partially invoked Currying
```
var answer = 0
const baseValue = value => multipleValue => value * multipleValue

const multiple = baseValue(2);
answer = multiple(5)
console.log(answer)          //10
```



