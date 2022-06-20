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

<h2 id="let">The let keyword</h2>
Let datatype has somehow same properties as C++ Datatypes.<br>
Let declaration is block scoped, and can not be redeclared in same scope. 

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
        console.log(this.firstName+" "+this.lastName)
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








