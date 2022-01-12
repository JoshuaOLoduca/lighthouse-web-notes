## Solving Problems With Pseudocode

### Loopy Lighthoush

below is a smart usecase for ternary function for the loopy lighthouse project
```js
for (const num of nums) {
  let output = "";

  if (num % 3 === 0) {
    output += "Loopy";
  }
  if (num % 4 === 0) {
    output += "Lighthouse";
  }
  console.log(output === "" ? num : output);
}
```

## Function Best Practices

- Give your functions precise verb/action based names

- Use camelCasedNames (like this one)

- Properly indent the function code

- Functions should focus on a single task: returning a value or causing a side effect.
  - Break your function into additional smaller functions if you find it doing two or more things
- Data needed by Functions should be passed in as parameters/arguments (i.e. local scope) instead of being accessed directly

## Rolling Dice Script Notes

Need to roll dice
  - a dice roll is randomly choosing a number

We can use
```js
Math.random()
```
  - Math.random() returns a number from 0 to just before 1
    - lowest is 0
    - highest is 0.999...
  - Multiply its output by desired max value
  ```js
  Math.random() * 10
  ```
  - Min value 0
  - max value 9.999..

#### What if we want a full number and not a float?

In comes
```js
Math.floor()
```
and
```js
Math.ceil()
```
- - -
Examples
```js
Math.floor(Math.random() * 10)
```
  - Min value 0
  - Max value 9

```js
Math.ceil(Math.random() * 10)
```
  - Min value 1
  - Max value 10