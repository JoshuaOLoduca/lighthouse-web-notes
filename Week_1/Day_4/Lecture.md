# Lecture Objectives
 - Functions as values
 - Calling a function vs passing
 - Callbacks
 - Anonymous functions
 - Arrow functions
 - Higher order functions


## Functions as values

```js
const sayHello = function() {
  console.log('Hello!');
};

//defines 'greetToConsole as [Function: sayHello]'
//because when we reference a function without ()
//it returns the definition of the function,
//and not run its 'actions'
//AKA, it gets the Value of the function
const greetToConsole = sayHello;

// () executes the function
//will print 'Hello!' to console
greetToConsole();
```

 ## Using functions in objects

### Scoping issue
 ```js
 const creature = {
   name: 'Caspian',
   type: 'Cat',
   // Scope of arrow functions are different than function () {}
   printNameWrong: () => {
     //this will print 'undefined'
     console.log(this.name)
   },
   printNameCorrect: function() {
     //this will print 'Caspian'
     console.log(this.name)
   }
 }
 ```

# Teacher Notes
### W01D04 - Callbacks
Hello, all! It was nice meeting you today! I know today's topic was pretty dense but I am attaching the lecture recording and the code that we worked on during lecture. I highly encourage you all to play around with the code and if you have any questions at all, please don't hesitate to reach out!

 - [lecture recording](https://vimeo.com/665743123/caa1e737fe)
 - [today's code](https://github.com/jcbain/east_2022_01_10/tree/main/w01d04_callbacks)

#### Objectives
 - [X] functions as values
 - [X] calling a function vs. passing a function
 - [X] callbacks!
 - [X] anonymous functions
 - [X] arrow functions
 - [X] higher order functions

### Functions as values
What's on the right hand side of a function expression is just a value. This value can be extended to passing them along to another variable.
```js
const sayHello = function(name) {
  console.log(`hello, ${name}`)
}

const printHello = sayHello;
printHello('Carl');
```
### Passing Functions to Functions
functions can be passed as arguments to other functions
```js
const sayHello = function(name) {
  return `hello, ${name}`;
}
const yellAtJames = function(anotherFunction) {
  const phrase = anotherFunction('james');
  const phraseYelled = phrase.toUpperCase();
  return `${phraseYelled}!!!`
}

const result = yellAtJames(sayHello);
console.log(result);
```
Functions that are passed to functions are called callbacks. In other words, a callback is a function that gets passed to another function to be invoked in a function.

### Anonymous functions
 - we don't have to pass a function variable to a higher order function as a callback but instead, we can pass an unnamed (anonymous) function directly inline.
```js
const yellAtJames = function(anotherFunc) {
  const statement = anotherFunc('James');
  return `${statement.toUpperCase()}!!!`
}

// anonymous functions

const result = yellAtJames(function(name) {
  return `You are awesome, ${name}`
});

console.log(result)
```
### Arrow functions
 - Arrow functions give us a syntactic alternative to using the function keyword
 - There are some gotchas around using the this keyword inside an arrow function, but if you aren't using this, arrow functions can be used interchangeably with "regular" functions
 - Arrow functions are often used as callbacks because they are shorter/cleaner to type
```js
// function expression
const sayHello = function(name) {
  console.log(`hello there, ${name}`);
};

sayHello('James');
// arrow function
const sayHello = (name) => {
  console.log(`hello there, ${name}`);
}

sayHello('Doug')
```


 # Breakout
 Syntaxically correct, but sorta cursed:
 ```js
 const 2ndName = function 1stName() {
   console.log('I am function1!')
 };

 1stName() //I am function1!
 2ndName() //I am function1!
 ```