## let vs var vs const
	- variable scope is the main difference between let and var
	- let's scope is with in the curly braces {} of functions, if, for, while etc
		function fn{}
		if {}
		for {}
		while {}
		do {} while 

	- while var mostly has global scope
	- const a = 5; // a = 6; will throw error as const values can not be changed.
	- const a = [1,2,3,4] // a[0] = 10; this is valid as a is a reference/pointer to the array or object. As long as the reference is not changing its fine.

## function definition

	var a = () => { 2;} // is same as the default JS function given below, also called as fat arrow functions 
	function a () {
		return 2;
	}

## this context
	- In ESMA5 context of this changes with function call.
	- IN ESMA6 context of this remains the same as it was during function definition. Context of this always remain the same

## default function arguements, similar to what it is in PHP, or other languages

## Object literals

	let a = 10;
	let b = 20;
	let obj = {
		a,
		b
	};
	// obj.a and obj.b will get initialized with 10 and 20.

## Rest operator

	Converts a list into an array.
		- Functions are more dynamic
		- You don't need to keep on modifying function args

	Example
	function sum(...toAdd) {

		//toAdd is an array, you dont need to define the number of arguments, it will automatically convert the passed arguments into an array
		let result = 0;
		for(let i=0; i < toAdd.length; i++) {
			result += toAdd[i];
		}
		return result;
	}
	sum(1,2,3); //will output 6

## Spread operator

	This is exact opposite of rest operator, by converting an array into a list

	forexample
	let arr = [1,2,3,4,5];

	Math.max(1,2,3,4,5); //outputs 5
	Math.max(arr); // throws error NaN
	//in ESMA6
	Math.max(...arr); //outputs 5 as well. 

## for of loop
	- Similar to phps foreach loop with a different syntax and key missing
	let nums = [1,2,3,4,5];
	for (let num of nums) {
		console.log(num); //1,2,3,4,5 
	}

## Template literals 
 	using back ticks. ``

	- multi line strings which was not possible before
	let a = `
		how r you man
		its been long
		`;
	- Using variables with in string

	let a = "Ahad";

	console.log(`hello world ${a}`);// outputs: hello world Ahad
## Destructure array

	Similar to `list` in php

	- Assigning variables
	let arr = [1,2,3];

	let [a,b,c] = arr; //shorter way of assigning values to variables from arrays

	console.log(a,b,c); //outputs 1,2,3
	- Using rest operator
		let [a, ...b] = arr;

		console (b); // outputs: 2,3
	- using defaults
		let [a, b, c, d] = arr; // d is undefined
		let [a, b, c, d = 20]; // = arr; d outputs 20// 
		let [a=20, b, c, d=20]; // a outputs 1 while d outputs 20. So wont be able to default a, because a value is already available in the array.

## Destructure Objects

	- Similar to destructuring arrays, the only difference is we use {} instead of [] while destructuring.
	- Also it does not need to be ordered unlike arrays, as property names are important than indexes.
	let obj = {
		"name": "Ahad",
		"age": 33
	}

	let {name, age} = obj; //name and age will hold the values that are in the object
