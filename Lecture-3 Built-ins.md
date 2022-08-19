## What is a WeakSet?

A WeakSet is just like a normal Set with a few key differences:

    a WeakSet can only contain objects
    a WeakSet is not iterable which means it can’t be looped over
    a WeakSet does not have a .clear() method

You can create a WeakSet just like you would a normal Set, except that you use the WeakSet constructor.
let student1 = { name: 'James', age: 26, gender: 'male' };
let student2 = { name: 'Julia', age: 27, gender: 'female' };
let student3 = { name: 'Richard', age: 31, gender: 'male' };

const roster = new WeakSet([student1, student2, student3]);
console.log(roster);
/*
 * Programming Quiz: Using Sets (3-2)
 *
 * Create the following variables:
 *     - uniqueFlavors and set it to a new WeakSet object
 *     - flavor1 and set it equal to `{ flavor: 'chocolate' }`
 *     - flavor2 and set it equal to an object with property 'flavor' and value of your choice!
 *
 * Use the `.add()` method to add the objects `flavor1` and `flavor2` to `uniqueFlavors`
 * Use the `.add()` method to add the `flavor1` object (again!) to the `uniqueFlavors` set
 */

 var flavor1={ flavor: 'chocolate' };
   var flavor2={ flavor: 'mango' };
   var uniqueFlavors =new Set();
   uniqueFlavors.add(flavor1);
uniqueFlavors.add(flavor2);
   uniqueFlavors.add(flavor1);
console.log(uniqueFlavors);

How to Create a Map

To create a Map, simply type:

const employees = new Map();
console.log(employees);

## Map {}

This creates an empty Map employee with no key-value pairs.
Modifying Maps

Unlike Sets, you can’t create Maps from a list of values; instead, you add key-values by using the Map’s .set() method.

const employees = new Map();

employees.set('james.parkes@udacity.com', { 
    firstName: 'James',
    lastName: 'Parkes',
    role: 'Content Developer' 
});
employees.set('julia@udacity.com', {
    firstName: 'Julia',
    lastName: 'Van Cleve',
    role: 'Content Developer'
});
employees.set('richard@udacity.com', {
    firstName: 'Richard',
    lastName: 'Kalehoff',
    role: 'Content Developer'
});

console.log(employees);

To remove key-value pairs, simply use the .delete() method.

employees.delete('julia@udacity.com');
employees.delete('richard@udacity.com');
console.log(employees);

    Map {'james.parkes@udacity.com' => Object {firstName: 'James', lastName: 'Parkes', role: 'Course Developer'}}

Again, similar to Sets, you can use the .clear() method to remove all key-value pairs from the Map.

employees.clear()
console.log(employees);
After you’ve built your Map, you can use the .has() method to check if a key-value pair exists in your Map by passing it a key.

const members = new Map();

members.set('Evelyn', 75.68);
members.set('Liam', 20.16);
members.set('Sophia', 0);
members.set('Marcus', 10.25);

console.log(members.has('Xavier'));
console.log(members.has('Marcus'));

    false
    true

And you can also retrieve values from a Map, by passing a key to the .get() method.

console.log(members.get('Evelyn'));

    75.68

















