# Function in ES6 JavaScript
Functions are one of the primary data structures in JavaScript; they've been around forever.

## Arrow functions
ES6 introduces a new kind of function called the arrow function. Arrow functions are very similar
to regular functions in behavior, but are quite different syntactically. 
The following code takes a list of names and converts each one to uppercase using a regular function:

const upperizedNames = ['Farrin', 'Kagure', 'Asser'].map(function(name) { 
  return name.toUpperCase();
});

The code below does the same thing except instead of passing a regular function to the map() method,
it passes an arrow function. Notice the arrow in the arrow function ( => ) in the code below:

## Convert a function to an arrow function

const upperizedNames = ['Farrin', 'Kagure', 'Asser'].map(function(name) { 
  return name.toUpperCase();
});

const names = ['Afghanistan', 'Aruba', 'Bahamas', 'Chile', 'Fiji', 'Gabon', 'Luxembourg', 'Nepal', 'Singapore', 'Uganda', 'Zimbabwe'];

const longNames = names.filter(function(name) {
  return name.length > 6;
});
console.log(longNames);

const longNames1 = names.filter(name=>name.length > 6);
console.log(longNames1);

const greet = name => `Hello ${name}!`;
name => `Hello ${name}!` ;
// empty parameter list requires parentheses
const sayHi = () => console.log('Hello Udacity Student!');
sayHi();
// multiple parameters requires parentheses
const orderIceCream = (flavor, cone) => console.log(`Here's your ${flavor} ice cream in a ${cone} cone.`);
orderIceCream('chocolate', 'waffle');


## Defaults and destructuring arrays
You can combine default function parameters with destructuring to create some pretty powerful functions!
function shippingLabel(name, address) {
  name = (typeof name !== 'undefined') ? name : 'Richard';
  address = (typeof address !== 'undefined') ?  address : 'Mountain View'
  return `To: ${name} In: ${address}`;
}


function ship(name="Iqrar",address="Chakwal"){
    return`To: ${name} In: ${address}`;
}
console.log(shippingLabel("Iqrar"));
console.log(ship("Iqrar"));

