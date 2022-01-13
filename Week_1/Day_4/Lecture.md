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