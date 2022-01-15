# Function scope weirdness
[Arrow Functions](https://youtu.be/Lq0UbHdjlc4?t=213)

notice how they set self to this right under the main function. this maintains the this scope to be used inside of that functions methods

# Recursion
### A function must have at least one recursive case and at least one base case in order to be recursive.
```js
function countEvenToTwelve(number) {
  if (number <= 12) { // Recursive Case
    console.log(number);
    // The function will call itself again and get closer to the base case
    countEvenToTwelve(number+2);
  }
  // Base case, do nothing when number > 12
}
countEvenToTwelve(0);
```

 - We refer to ```number <= 12``` as a recursive case, because as long as this is true, the function will continue to call itself.
 - We refer to ```number > 12``` as a base case. If this is true, the function will not call itself.

#### Recursion vs Iteration
 ```js
 const printItems = function(array) {
  for (let item of array) {
    if (Array.isArray(item)) {
      printItems(item);
      continue;
    }
    console.log(item);
  }
}

const printItemsIteration = function(array) {
  while (array.length > 0) {
    const element = array.shift();

    if (Array.isArray(element)) {
      element.reverse().forEach((newElement)=> {
        array.unshift(newElement);
      });
    } else {
      console.log(element);
    }
  }
}

const array = ["😎", [["💩", ["🤗"]], [[["😼"]], "😂"]]];
printItemsIteration(array);
printItems(array);
 ```