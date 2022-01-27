Magic of closures
```js
const functionWrapper = (someValue) => {
	const bob = { a: 1 };

	const someFunction = (times) => {
		for (let i = 0; i < times; i++) {
			console.log(someValue);
		}
	};

	const someOtherFunction = (value) => {
		console.log(value + someValue);
	};

	return { bob, someFunction, someOtherFunction };
};
// Line 16
const { someFunction, someOtherFunction } = functionWrapper(10);
const bobby = functionWrapper(15);

someFunction(2); // Will print 10 (from line 16) 2 times
someOtherFunction(20); //will add 20 to 10 (from line 16) and output to the console

bobby.bob;

const bob = {
	method: () => {
		console.log(this);
	},
};

bob.method();
```