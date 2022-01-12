# Primitive javascript Data types
 - undefined
 - null
 - boolean
 - string
 - number
 - symbol (Introduced in ES6 and not something we need to focus on right now)

 Everything js type not listed here are objects.

## What are objects
Objects:

 - Contain key-value pairs; each key maps to a value
 - Contain keys which are always strings (or symbols, but it's less common and not important right now)
 - Have unique keys; the same key cannot appear twice in an object
    - if keys do share the same name, the last one of the same name will be its definition
 - Have their keys point to values which can be of any type

 Objects can also be thought 0f as a 2 column table

## Using Objects
 
### To access keys we can use:

 Dot Notation
 ```Object.key```

 Braket Notation
```Object['key']```

### To populate

```js
const person = {
  name: "Paul",
  address: {
    street: "310 W 95th",
    city: "New York",
    zipCode: 10027
  }
};
```
Notice how a key can also be an object.
 - It can also be a function
