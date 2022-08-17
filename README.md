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


## Destructuring values from an array
const point = [10, 25, -34];
const [x, y, z] = point;
console.log(x, y, z);

## Destructuring values from an object
var person={
    name:"iqrar",
    age:22,
    gender:"male"
}
const{name,age,gender}=person;
console.log(name,age,gender);

### Directions:

Use array destructuring to pull out the three colors from the array of things and store them into the variables one, two, and three.
const things = ['red', 'basketball', 'paperclip', 'green', 'computer', 'earth', 'udacity', 'blue', 'dogs'];

const [one,,,two,,,,three]=things
const colors = `List of Colors
1. ${one}
2. ${two}
3. ${three}`;

console.log(colors);

## Object literal shorthand

let name="iqrar";
let age=22;
let  gender="male";
const person ={name,age,gender,print:function(){
    console.log(`Hello my name is ${name} and Im ${age} year old and Im ${gender}.`);
}
}
console.log(person.print());
### for...of loop 
Really the biggest downside of a for loop is having to keep track of the counter and exit condition.
The for...in loop improves upon the weaknesses of the for loop by eliminating the counting logic and exit condition.
const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (const index in digits) {
  console.log(digits[index]);
}

### Directions:

Write a for...of loop that:

    loops through each day in the days array
    capitalizes the first letter of the day
    and prints the day out to the console

Your code should log the following to the console:

    Sunday
    Monday
    Tuesday
    Wednesday
    Thursday
    Friday
    Saturday

/*
 * Programming Quiz: Writing a For...of Loop (1-4)
 */

const days = ['sunday', 'monday', 'tuesday', 'wednesday', 'thursday', 'friday', 'saturday'];
for(const day of days){
   
    console.log(day[0].toUpperCase() + day.slice(1));
}



## Spread operator
The spread operator, written with three consecutive dots ( ... ), is new in ES6 and gives you the ability to expand
const books = ["Don Quixote", "The Hobbit", "Alice in Wonderland", "Tale of Two Cities"];
console.log(...books);

/*
 * Instructions: Use the spread operator to combine the `fruits` and `vegetables` arrays into the `produce` array.
 */

const fruits = ["apples", "bananas", "pears"];
const vegetables = ["corn", "potatoes", "carrots"];
const produce = [...fruits,...vegetables];
console.log(produce);


## Rest parameter
The rest parameter, also written with three consecutive dots ( ... ), allows you to represent an indefinite number of elements as an array. This can be helpful in a couple of different situations.
const order = [20.17, 18.67, 1.50, "cheese", "eggs", "milk", "bread"];
const [total, subtotal, tax, ...items] = order;
console.log(total, subtotal, tax, items);


#Variadic functions
Another use case for the rest parameter is when you’re working with variadic functions. Variadic functions are functions that take an indefinite number of arguments.
function sum(...nums) {
  let total = 0;  
  for(const num of nums) {
    total += num;
  }
  return total;
}

## Directions:

Use the rest parameter to create an average() function that calculates the average of an unlimited amount of numbers.

    TIP: Make sure to test your code with different values. For example,

    average(2, 6) should return 4
    average(2, 3, 3, 5, 7, 10) should return 5
    average(7, 1432, 12, 13, 100) should return 312.8
    average() should return 0
/*
 * Programming Quiz: Using the Rest Parameter (1-5)
 */

// your code goes here

function average(...nums) {
    let ave=0;
    for(let num of nums){
        ave=(ave+num)
    }
    if (nums.length===0){
         ave=0;
         return ave;
    }
    ave=ave/nums.length
    return ave;
     
}

console.log(average(2, 6));
console.log(average(2, 3, 3, 5, 7, 10));
console.log(average(7, 1432, 12, 13, 100));
console.log(average());
