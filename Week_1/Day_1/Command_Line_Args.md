# Command Line Args Intro

###### Understanding how to use cmd args with node program

we pass args to the program using the following template
```console
$ [runtime] [script_name] [argument-1 argument-2 argument-3 ... argument-n]
```
Here is an example for node
```console
$ Node myProgram.js --flag flag_data -f f_data
```
### Ok, but why?
If we design a program to use cmd args. We are able to make it flexible.

We also wont have to open up the file and manually edit vars.

### How?
we use the following built in var of the array data type
```js
process.argv
```
process.argv[0] and process.argv[1] will always be strings to the directories of the node executable and the program location respectively.

##### Example
```js
'use strict';

for (let j = 0; j < process.argv.length; j++) {
    console.log(j + ' -> ' + (process.argv[j]));
}
```
###### Output
```console
$ node processargv.js tom jack 43
0 -> /home/vagrant/.nvm/versions/node/v12.22.8/bin/node
1 -> /vagrant/lighthouse-bootcamp/w1/d1-focal/processargv.js
2 -> tom
3 -> jack
4 -> 43
```

### Can we make it cleaner?
Yes! Since its an array we can slice the first 2 off
```js
process.argv = process.argv.slice(2);
```

##### Example
```js
'use strict';

process.argv = process.argv.slice(2);

for (let j = 0; j < process.argv.length; j++) {
    console.log(j + ' -> ' + (process.argv[j]));
}
```
###### Output
```console
$ node processargv.js tom jack 43
0 -> tom
1 -> jack
2 -> 43
```

#### Ok, thats better. but Can we make it easier to work with? relying on array indexes make the input order sensitive
Arent you smart cookie!
We can use a node packaged called

[minimist](https://www.npmjs.com/package/minimist)


Which will assign data to their flags.
