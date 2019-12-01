# primitive types
> number, string, boolean, object

> NaN -> not a number i.e. 0/0

```js
 let song = "london calling";
 typeof song
 "string"
```
## string escapes and template literals
``` js
\n
\'
\"
\\
`sdsdfd ${thevariable} ..ldd`
```
## null, undefined
```js
//null means a variable have a value of null, the variable is assigned

let color1 = null;

let color2;

//undefined means variable is not assigned to any value 
```
## == vs ===
> == checks equality of values while coerces both values to the same type
> === checks both values and types

## Falsy values
```js
false
0
""
null
undefined
NaN
```
> the rest normal values are truthy
## switch statement
> the same with Java

## Ternary operator
```js
<condition> ? trueExp : falseExp;
```

## functions for numbers
```js
// math methods
Math.PI
Math.round(4.9)
Math.abs(-455)
Math.pow(2, 5)
Math.floor(3.9999)
//parse strings to numbers
parseInt('24')
parseFloat('24.333')

```

## array
```js
new Array();
[]
push() // Add to the end of the original array, return the length of the array
pop() // Remove from the end, return the removed element
shift() // Remove from the start, return the removed element
unshift() // Add to the start, return the length of the array
concat([1,2,3], [3,4,5]) 
[1,2,3].includes(2)
[1,2,3].indexOf(3)
[1,2,3].join('-') // Create a string from an array
[1,2,3].reverse()
[1,2,3].slice(0,4) // Copy portion of an array
[1,2,3].splice(0, 0, 'newbie') // Change the array content by add 'newbie' to the next of index 0
[1,2,3].splice(3, 2) // remove 2 elements started from index 3
[1,2,3].splice(3, 2, 'ione', 'itwo') // remove 2 elements started from index 3
// If (a,b) return `< 0`, then it sorts a before b
[].sort((a,b) => (a-b)) 
```

## object
```js
Object.keys(movieReviews);
Object.values(movieReviews);
//for of works with iterables
for(let movie of Object.keys(movieReviews)) {
    console.log(movie, movieReviews[movie]);
}
```

## functions
```js
// Functions could be an expression value to a variable
const sum = function(x, y) {
    return x+y;
}

// Functions could be as arguments, and return value
// Callback functions are passed in as arguments
function callTwice(func) {
    func();
    return func();
}

// Hoisting: var variables hoist up to the beginning of the code, so when tring to access the vairable, it looks declared but not defined.
console.log(animal);
var animal = 'Tapir;

```

## Array callback functions
```js
[1,2,3].forEach(function(num) {
    console.log(idx, num);
});

// map() creates a new array with elements from callback
const doubles = [1,2,3].map(num) => num*2)
//
['123','222','333'].find(num => num.includes('1'));
// filter() creates a new array with all elements that pass the callback check
[1,3,4].filter(n=> n%2===1);
// wether every item passes the check
[1,2,3].every(num => num.length >1);
[1,2,3].every(num => num.length >1);
// wether any item passes the check
[1,2,3].some(num => num.length>1);
// reduce() results in a single value
['1','2','3'].reduce((accumulator, currentValue) => accumulator+currentValue, 'inital');
[1,]
//
functin multiply(x=1, y=0) {
    return x+y;
}
functin multiply(...[45,23,13]) {
    return x+y;
}
const nums1 = [1,2,3];
const nums2 = [4,5,6];
// Spread in an array
const nums = [...nums1, ...nums2];
// Spread in objects
const nums = { ...nums1, 4, 5, 6};
const nums = { ...nums1, ...nums2};
// 'string' type could be spreaded
const nums = {...'hello', ...nums1};
// ...nums as a parameter
const multiply = (...nums) => {
    return nums.reduce((total, curr) => total + curr);
}
//
const nums1 = [1,2,3,4,5];
const [first, , , forth] = nums;
const [first, ...others] = nums;
const name = {first: "Eliud", last:"Kip", country: "Kenya"}
const {first, last} = name;
const {first, ...other} = name;
const result = [
    {first: "Eliud", last: "Kipchoge"},
    {first: "Eliud", last: "Kipchoge", country: "Ethiopia"}
]
const [{first: goldWinder}, {country}] = results;
function print(person) {
    const {first, last, title} = person;
    console.log(`${first} ${last} ${title}`);
}
// {host: 'Jools Hoooland', Director: 'James'}
const role = 'host';
const person = 'Jools Hoooland';
const role2 = 'Director';
const person2 = 'James';
const team = {
    [role]: person,
    [role2]: person2
}
```

## this
#### `this` in methods could access properties of the object 
> object.method();
#### `this` refers to window if just call the function in the browser console
> method();
#### arrow functions cannot directly access object `this`, instead it needs a outer function to access `this`, so we dont use arrow funcions in objects
```js
// As an inner function, array function could access its outer function's this
const annoyer = {
    phrases: [],
    pickPhrase() {
        const idx = Math.random();
        return phrases[idx];
    },
    start() {
        setInterval(() => {
            console.log(this.pickPhrase())
        },3000)
    }
}
```
## events
```js
window.addEventListener('scroll', function() {
    console.log('stop scrolling.');
});
button.addEventListener('click', function() {
    button.innerText = 'You got me!';
    document.body.style.backgroundColor = 'green';
})
```