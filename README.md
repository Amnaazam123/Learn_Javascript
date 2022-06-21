# Learn Javascript
### Data Types:
```
let length = 16;                               // Number
let num = 16.32                                // Number
let lastName = "Azam";                         // String
const cars = ["Saab", "Volvo", "BMW"];         // Arrays
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
Note : A regular function declaration defines a function that will be executed when it is invoked. A function expression is similar to a function declaration, with the difference that it can be stored in a variable. As soon as the function is defined with an expression, it is invoked.Lter on it is just used.

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

# 🤩🤩🤩🤩 WELCOME Here!! These are some Tasks asked by my Mentor 🤩🤩🤩🤩
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






