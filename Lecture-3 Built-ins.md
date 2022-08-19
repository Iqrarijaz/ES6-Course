# Built-ins
## Symbols
A symbol is a unique and immutable data type that is often used to identify object properties.
To create a symbol, you write Symbol() with an optional string as its description.
const sym1 = Symbol('apple');
console.log(sym1);

const sym2 = Symbol('banana');
const sym3 = Symbol('banana');
console.log(sym2 === sym3);


const bowl = {
  'apple': { color: 'red', weight: 136.078 },
  'banana': { color: 'yellow', weight: 183.15 },
  'orange': { color: 'orange', weight: 170.097 }
};
The bowl contains fruit which are objects that are properties of the bowl. But, we run into a problem when the second banana gets added.
const bowl = {
  'apple': { color: 'red', weight: 136.078 },
  'banana': { color: 'yellow', weight: 183.151 },
  'orange': { color: 'orange', weight: 170.097 },
  'banana': { color: 'yellow', weight: 176.845 }
};
console.log(bowl);
Object {apple: Object, banana: Object, orange: Object}
Instead of adding another banana to the bowl, our previous banana is overwritten by the new banana being added to the bowl. To fix this problem, we can use symbols.
const bowl = {
  [Symbol('apple')]: { color: 'red', weight: 136.078 },
  [Symbol('banana')]: { color: 'yellow', weight: 183.15 },
  [Symbol('orange')]: { color: 'orange', weight: 170.097 },
  [Symbol('banana')]: { color: 'yellow', weight: 176.845 }
};

console.log(bowl);
Object {Symbol(apple): Object, Symbol(banana): Object, Symbol(orange): Object, Symbol(banana): Object}
By changing the bowl’s properties to use symbols, each property is a 
unique Symbol and the first banana doesn’t get overwritten by the second banana.
The Iterator Protocol
The iterator protocol is used to define a standard way that an object
produces a sequence of values. What that really means is you now have 
a process for defining how an object will iterate. This is done through implementing the .next() method.
How it Works
An object becomes an iterator when it implements the .next() method. 
The .next() method is a zero arguments function that returns an object with two properties:
    1. value : the data representing the next value in the sequence of values within the object 
    2. done : a boolean representing if the iterator is done going through the sequence of values
        ◦ If done is true, then the iterator has reached the end of its sequence of values. 
        ◦ If done is false, then the iterator is able to produce another value in its sequence of values. 
Here’s the example from earlier, but instead we are using the array’s 
default iterator to step through the each value in the array.
const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
const arrayIterator = digits[Symbol.iterator]();

console.log(arrayIterator.next());
console.log(arrayIterator.next());
console.log(arrayIterator.next());
Object {value: 0, done: false}
Object {value: 1, done: false}
Object {value: 2, done: false}


## set
/*
 * Programming Quiz: Using Sets (3-1)
 *
 * Create a Set object and store it in a variable named `myFavoriteFlavors`. Add the following strings to the set:
 *     - chocolate chip
 *     - cookies and cream
 *     - strawberry
 *     - vanilla
 *
 * Then use the `.delete()` method to remove "strawberry" from the set.\*/
const myFavoriteFlavors = new Set([]);
myFavoriteFlavors.add("chocolate chip");
myFavoriteFlavors.add("cookies and cream");
myFavoriteFlavors.add("strawberry");
myFavoriteFlavors.add("vanilla");
myFavoriteFlavors.delete("strawberry")
console.log(myFavoriteFlavors)
