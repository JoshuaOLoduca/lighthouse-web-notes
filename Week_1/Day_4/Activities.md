## Terms
[First-class Objects](https://en.wikipedia.org/wiki/First-class_citizen)
  - In programming language design, a first-class citizen (also type, object, entity, or value) in a given programming language is an entity which supports all the operations generally available to other entities. These operations typically include being passed as an argument, returned from a function, modified, and assigned to a variable.

## Callbacks
### Bad method for desired result
Better format would to format forEach to use an anonymous function so it can
1. to do some logic
2. take in as many args as desired
```js
// The second argument/parameter is expected to be a (callback) function
const findWaldo = function(names, found) {
  //passing the function after the callback sets it to "this" in the callbackFunction
  names.forEach(looper, found);
}

const looper = function(name, index, _) {
  if (name === "Waldo") {
    //We are executing ActionWhenFound with the vars of Name and Index
    this(name, index);   // execute callback
  }
}

const actionWhenFound = function(name,index) {
  console.log(`Found ${name} at index ${index}!`);
}

findWaldo(["Alice", "Bob", "Waldo", "Winston"], actionWhenFound);
```

## Stretch

### Sorting
- Default array sort in javascript is lexigraphical.
  - also known as alphabetical.
  - this also applies to numbers.
    - yes, numbers are sorted alphabetically
      - yes, its dumb.
  - [here is documentation for sorting numerically](http://www.javascriptkit.com/javatutors/arraysort.shtml)

## Resources
 - [Understanding Javascript Promises](https://attachments.convertkitcdnn2.com/343082/c6984633-5363-4ca2-b662-47b36693c5b2/understanding-javascript-promises.pdf)

 - [Video on Arrow functions - Fun Fun Function](https://youtu.be/6sQDTgOqh-I)

 - [Video on Higher-order functions - Fun Fun Function](https://youtu.be/BMUiFMZr7vk)

  - [Video on Array.Map - Fun Fun Function](https://youtu.be/bCqtb-Z5YGQ)

 - [Vim Cheat sheet](http://www.viemu.com/vi-vim-cheat-sheet.gif)
  ![Vim Cheat sheet](http://www.viemu.com/vi-vim-cheat-sheet.gif)