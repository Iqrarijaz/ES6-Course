## Welcome to the course on ES6! 👋🏼

This course is all about the new changes brought to the JavaScript programming language.
# Syntax
There are now two new ways to declare variables in JavaScript: let and const.

Up until now, the only way to declare a variable in JavaScript was to use the keyword var. To understand why let and const were added, it’s probably best to look at an example of when using var can get us into trouble.

## cases
The big question is when should you use let and const? The general rule of thumb is as follows:

    use let when you plan to reassign new values to a variable, and
    use const when you don’t plan on reassigning new values to a variable.
 
 
This works alright, but it gets more complicated when you need to build multi-line strings.

let note = teacher.name + ',\n\n' +
  'Please excuse ' + student.name + '.\n' +
  'He is recovering from the flu.\n\n' +
  'Thank you,\n' +
  student.guardian;

let message = `${student.name} please see ${teacher.name} in ${teacher.room} to pick up your report card.`;

## Destructuring
Destructuring borrows inspiration from languages like Perl and Python by allowing you to specify the elements you want to extract from an array or object on the left side of an assignment. It sounds a little weird, but you can actually achieve the same result as before, but with much less code; and it's still easy to understand.


### Destructuring values from an array
const point = [10, 25, -34];
const [x, y, z] = point;
console.log(x, y, z);

### Destructuring values from an object
var person={
    name:"iqrar",
    age:22,
    gender:"male"
}
const{name,age,gender}=person;
console.log(name,age,gender);
