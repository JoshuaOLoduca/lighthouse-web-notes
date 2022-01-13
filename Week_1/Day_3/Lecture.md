# Introduction the Objects in JS

- Prim data types
- fundamentals
- keys
- functions in objects

## Sources
[Lecture Video](https://vimeo.com/665317404/7910e8c720)

[Teacher Notes](https://github.com/FrancisBourgouin/lectures-2022-east-jan10)

## Tips

Try to not modify values. but to make new ones holding the updated version of the "edited" one
- - -
Falsey's is returned on primitive data types that lack definitive information
- - -
Objects cant, by default, be falsey. since to exist, they need to have structure. and that structure provides definitive information

but we can look at keys (of primitive data types) in the object and see if they are truthy/falsey.

#### How does that work?

because objects can be made out of primitive data types.

And those can be truthy/falsey

## Object facts
1. Object is not iterable
2. Object is a structual type
3. there are 2 notations for accessing keys values
## Object Variable Handling
Const object vars refer to objects in memory.

```js
const firstCoffee = {key: value}
const secondCoffee = firstCoffee
```
```firstCoffee``` and ```secondCoffee``` both have the same reference. so editing one will edit the others
### Working with its data
 Dot Notation
 ```Object.key```
 ```Object.key = "value"/function```

 Braket Notation
```Object['key']```
```Object['key'] = "value"/function```

#### To populate

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

### Accessing Keys
Sample Object
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
<br />
<br />

To get street
##### Dot Notation
```js
let street = person.address.street;
```
##### Bracket Notation
```js
let street = person['address']['street'];
```
### Iteration
To get keys of an object
#### keys
##### For In
```js
for (let key in object) {
  // Returns the value of key
  console.log(object[key])
  // Returns Key name
  console.log(key)
}
```
##### For Of Loop
```js
let keys = Object.keys(object);
for (let key of keys) {
  // Returns the value of key of object supplied
  console.log(object[key])
  // Returns Key name
  console.log(key)
}
```
#### values
##### For Of Loop
```js
let values = Object.values(object);
for (let value of values) {
  // Returns the value
  console.log(value)
}
```



## Resources
[Javascript code visualizer](http://pythontutor.com/javascript.html)