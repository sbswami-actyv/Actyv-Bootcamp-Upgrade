# **Variable**

`Variable` which holds the data value and it can be changed anytime.

```js
var a = 10;
a = "String";
console.log(a); // String
```

_JavaScript_ uses reserved keyword `var`,`let` and `const`  to declare a variable.


## **Var :-**

It is used to declare a variable and, optionally, we can `initialize` the value of that variable.

- The var statement declares a local variable in a [Function Scope](#FunctionScope).

- [Hoisting](#Hoisting) works in var keyword.


## **Let :-**

The let statement declares a local variable in a [Block Scope](#BlockScope).


## **const :-**
const statement values can be assigned once and they cannot be reassigned. The scope of const statement works similar to let statements.

```js
const number = 42;
const number = 45;
// SyntaxError: Identifier 'number' has already been declared
```


> ## **Scope :-)**   

Scope determines the visibility or accessibility of a variable or other resource in the area of your code.



## **GlobalScope**

The area outside all the functions is consider the global scope and the variables defined inside the global scope can be accessed and altered in any other scopes.

<details>
<summary>Examples</summary>

```js
//global scope
var fruit = 'apple'
console.log(fruit);        //apple

function getFruit(){
    console.log(fruit);    //fruit is accessible here
}

getFruit();                //apple
```
</details>


> |||||||

## **LocalScope**


Variables declared inside the functions become Local to the function and are considered in the corresponding local scope.


<details>
<summary>Examples</summary>

```js
//global scope
function foo1(){
    //local scope 1
    function foo2(){
        //local scope 2
    }
}

//global scope
function foo3(){
    //local scope 3
}

//global scope
```
</details>


Local scope can be divided into function scope and block scope. The concept of block scope is introduced in ECMA script 6 (ES6) together with the new ways to declare variables:- const and let.


### `FunctionScope`
The variable is visible  only within the function. You can't access it outside the function

<details>
<summary>Code Snippet</summary>

```js
function foo(){
    var fruit ='apple';
    console.log('inside function: ',fruit);
}

foo(); //inside function: apple
console.log(fruit);//error: fruit is not defined 

```

</details>


### `BlockScope`


A block scope is the area within `if, switch conditions or for and while loops`.  whenever you see {curly brackets}, it is a block. In ES6, const and let keywords allow developers to declare variables in the block scope, which means those variables exist only within the corresponding block.

<details>
<summary>Code Snippet</summary>

```js
function foo(){
    if(true){
        var fruit1 = 'apple';        //exist in function scope
        const fruit2 = 'banana';     //exist in block scope
        let fruit3 = 'strawberry';   //exist in block scope
    }
    console.log(fruit1);//apple
    console.log(fruit2);//error: fruit2 is not defined
    console.log(fruit3);//error: fruit3 is not defined
}

foo();



```
</details>



> ||||||

## **LexicalScope**
 Lexical scope means the children scope have the access to the variables defined in the parent scope. The children functions are lexically bound to the execution context of their parents.



<details>
<summary>Code Snippet</summary>

```js
 function foo1(){
    var fruit1 = 'apple';        
    const fruit2 = 'banana';     
    let fruit3 = 'strawberry';
    function foo2(){
        console.log(fruit1);
        console.log(fruit2);
        console.log(fruit3);
    }
    foo2();
}

foo1();

//result:
//apple
//banana
//strawberry
```
</details>

> ||||||


## **Hoisting**

Hoisting in JavaScript is a feature in which the interpreter moves the function and variable declarations to the top of their containing scope. It means that variable declarations, wherever they occur, are processed before any code is executed. Note that hoisting only moves the declaration and not the assignment. This will be clearer in the examples below.



![hoisting](https://chiendt.files.wordpress.com/2017/05/screenshot-at-may-16-14-57-31.png)








**_Questions:-_**

1. Different between let,var and const ?

<details>
<summary>Answer</summary>

Keyword | Scope | Hoisting | Can Be Reassigned | Can Be Redeclared
------- | ------- | ------- | ------- | -------
Keyword | Scope | Hoisting | Can Be Reassigned | Can Be Redeclared
var | Function scope | Yes | Yes | Yes
let | Block scope | No | Yes | No
const | Block scope | No | No | No

</details>

2. How to make a variable global in this code ?


```js
{
let a = 10;
let b = 13;
let c = 20;
}
```

<details>
<summary>Answer</summary>
A can become a global variable without using  a keyword because js will by default take this var.

```js
{
 a = 10;
let b = 13;
let c = 20;
}

// But this is not a good approach because anyone can manipulate with our object easily.
```
</details>


3. If var is functional scope.Where is the function in this code?
<details>
<summary>Answer</summary>


```js
{
 var a = 10;
 var b = 13;
 var c = 20;
}

```
In js main function runs first. In other programming languages like Java, c++. We have to write the main function but it’s already by default store  in js when code will compile first main function will run.

</details>

4. How hoisting works with var ?

<details>
<summary>Answer</summary>

Hoisting works with var because at compiling time the variable if declared with the var keyword will get stored in window object.

```js
let b = 10;
var a = 20;

window.b; //undefined  because b is not store in window object.

window.a // 20 because a stored in window object.
```


</details>

5. Why let and const don’t work with hoisting ?

<details>
<summary>Answer</summary>
let and const keywords value will store in memory while executing time.
</details>