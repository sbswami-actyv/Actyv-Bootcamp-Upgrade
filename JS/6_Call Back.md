
# Call Back
>A callback is a function that is to be executed after another function has **finished executing** — hence the name '`call back`'.  In JavaScript, functions are objects. ... Any function that is passed as an argument is called a **callback function.**

A callback function, also known as a [higher-order function](#higher-order-function), is a function that is passed to another function (let's call this other function “otherFunction”) as a parameter, and the callback function is called (or executed) inside the otherFunction.


![Callback example: Reference Google](https://www.educative.io/api/edpresso/shot/6533893308022784/image/5816170181558272)


# Why Do We Need CallBack
JavaScript is an [event driven language](#event-driven-language). This means that instead of waiting for a response before moving on, JavaScript will keep executing while listening for other events.


```js
function first(){
  console.log(1);
}
function second(){
  console.log(2);
}
first();
second();

```

`OUTPUT:`
```
1
2

```


>But what if function `first` contains some sort of code that can’t be executed immediately? **For example**, an API request where we have to send the request then wait for a response? To simulate this action, were going to use `setTimeout` which is a JavaScript function that calls a function after a set amount of time. We’ll delay our function for 500 milliseconds to simulate an API request.


```js
function first(){
  // Simulate a code delay
  setTimeout( function(){
    console.log(1);
  }, 500 );
}
function second(){
  console.log(2);
}
first();
second();

```
`OUTPUT:`
```
2
1

```

## Explanation : 
>Even though we invoked the first() function first, we logged out the result of that function after the second() function. It’s not that JavaScript didn’t execute our functions in the order we wanted it to, it’s instead that JavaScript didn’t wait for a response from first() before moving on to execute second().

> Because you can’t just call one function after another and hope they execute in the `right order`. Callbacks are a way to make sure certain code doesn’t execute until other code has already finished execution.


# Creating CallBack

```js

function doHomework(subject, callback) {
  console.log(`Starting my ${subject} homework.`);
  callback();
}
function alertFinished(){
  console.log('Finished my homework');
}
doHomework('math', alertFinished);

```

`OUTPUT :`
```js
 Starting my math homework.
 Finished my homework

```

## Explanation:
It the doHomework function we are passing the alertFinished function as an argument.Console inside the doHomework function will get executed and the callback() will call the function alertFinished for execution and the console inside it will be executed.


## Another Example:

```js
function first(a,callback){
    console.log(1)
    callback();
  }
  function second(){
    console.log(2);
  }
  first("hello",second);

```
`OUTPUT:`
```
1
2

```






## Event Driven Language
>Event-driven programming is a programming paradigm in which the flow of program execution is determined by events - `for example : ` a user action such as a mouse click, key press, or a message from the operating system or another program.





# Higher Order Function
>Higher-Order function is a function that receives a `function as an argument` or `returns the function as output`..





`For example`: **map()**, **filter()** and **reduce()** are some of the Higher-Order functions built into the language.


![Higher order function: Reference google](https://miro.medium.com/max/812/1*-kjr_j7fmoQNIGLf8eZIgw.jpeg)

## Normal Function
```js
function add (a) {
  return function (b) {
    return a + b;
  }
}
add(3)(4);

```
`OUTPUT:`
```js
7
```

## Arrow Function
```js

add=(x)=>(y)=> x+y;

console.log(add(1)(2));

```
`OUTPUT:`
```js
3
```


```

Reference : https://www.freecodecamp.org/news/a-quick-intro-to-higher-order-functions-in-javascript-1a014f89c6b




```