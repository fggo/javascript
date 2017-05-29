* [Introduction](#introduction-to-javascript)
* [Function](#function)
* [Loops](#loops)
* [Control Flow](#control-flow)
* [Data Structure](#data-structure)
* [Object](#object)

# Introduction
## Basic
```javascript
"myName"
"myName".length
3+4
3*4/2
121/10
121%10 //modulo; 121%10 === 1

eggplant //Reference Error!
```

## Interactive JavaScript
```javascript
confirm("Welcome. Click OK to continue!")
prompt("Where are you from?") //ask for user input
```

## Variable Types
Primitive data types
```javascript
//1.number
3.14
3
2e10
2e-10
//2.string
"This is a string variable".length
//3.boolean
true
false
"I'm coding like a champ".length === 10 
```

## Console Output
```javascript
console.log();
```

## Comparison
```javascript
console.log(15 > 4); // true
console.log("Goody Morning".length < 8); //false
console.log(8*2 === 16); //strict equality
console.log(8*2 !== 16); //strict inequality
```

## Control Flow
```javascript
if ( "lalala".length < 2*5)
	console.log("short string")
else if("lalala".length === 2*5)
	console.log("string length is 10")
else{
	console.log("too long");
	console.log("not a short string");
}
```

## Substring
find 4th up to and including 7th of a string
```javascript
"wonderful day".substring(3, 7) //derf
console.log("January".substring(0,3)) //Jan
```

## Variables
```javascript
var pi = 3.1415
var myName = "eee"
console.log(pi);
```

## Reassign String
string is immutable; letters can not be mutated; instead reassign to another string value
```javascript
var myName = "icecream"
myName = myName.substring(0,2)
```

## Example
```javascript
if(confirm("I am ready to play!"))
	console.log("Welcome to our New game")

var age = prompt("what's your age?")
if(age < 13) console.log("You're too young, but that's okay");
else console.log("Enjoy the game")

var rating = prompt("Please rate our game")
if (rating >= 9) console.log("Thank you.")
else console.log("Too bad")
```

# Function
function is a variable. function name follows 'lowerCamelCase'
```javascript
var divideByThree = function(number){
	var val = number / 3;
	console.log(val);
};
divideByThree(6);
```

function returns value
```javascript
var getCostOfFive = function(cost){
	console.log(5*cost);
}
var orangeCost = function(){
	return 5; //returns
}
getCostOfFive(orangeCost())
```

## Global vs Local Variables
```javascript
var globalVar = "global variable";
var foo = function() {
	var localVar = "local variable"
	console.log(globalVar);  //ok
}
console.log(localVar); //error!

/*another example*/
var my_number = 7; //this has global scope
var timesTwo = function(number) {
	var my_number = number * 2;
	console.log("Inside the function my_number is: ");
	console.log(my_number); //local
}; 
timesTwo(7); //14

console.log("Outside the function my_number is: ")
console.log(my_number); //7; prints global
```

## Example
Rock paper scissors
```javascript
var userChoice = prompt("Do you choose rock, paper or scissors?");
var computerChoice = Math.random();
if (computerChoice < 0.34) {
	computerChoice = "rock";
} else if(computerChoice <= 0.67) {
	computerChoice = "paper";
} else {
	computerChoice = "scissors";
} console.log("Computer: " + computerChoice);

var compare = function(choice1, choice2){
	if (choice1 === choice2)
		return "The result is a tie!"
	else if(choice1 === "rock"){
		if(choice2 === "scissors")
			return "rock wins"
		else
			return "paper wins"
	}
	else if(choice1 === "paper"){
		if(choice2 === "rock")
			return "paper wins"
		else
			return "scissors wins"
	}
	else{ //choice1 === "scissors"
		if(choice2 === "rock")
			return "rock wins"
		else
			return "scissors wins"
	}
}
compare(userChoice, computerChoice)
```

# Loops

## for Loops
```javascript
for (var counter = 1; counter <= 10; counter++) {
	console.log(counter);
}
for (var i = 5; i < 51; i+=5) {
	console.log(i);
}
for (var i = 10; i >= 0; i--) {
	console.log(i);
}
```

## Array
```javascript
var junk = ["a", "b", 1,2]
console.log(junk)

for(var i =0; i<junk.length; i++)
	console.log("junk > " + junk[i]) //print (i+1)th element

for(var i in junk)
	console.log(i)
```

## for each in
[for...in](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in) 
statement iterates over the enumerable properties of an object, in original insertion order.

[for each...in](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for_each...in)
statement iterates a specified variable over all values of object's properties. 
For each distinct property, a specified statement is executed.
a similar statement as for...in, but iterates over the values of object's properties, rather than the property 
names themselves (deprecated)

## Example
```javascript
text = "Blah blah blah blah blah blah Eric blah blah blah \
Eric blah blah Eric blah blah blah blah blah blah blah Eric";
var myName = "Eric";
var hits = [];

for(var i = 0; i < text.length; i++) {
	if (text[i] === "E") {
		for(var j = i; j < (myName.length + i); j++){
			hits.push(text[j]);
		}
	}
}

if (hits.length === 0) {
	console.log("Your name wasn't found!");
} else {
	console.log(hits);
}
```

## while Loops
```javascript
var coinFace = Math.floor(Math.random() * 2);

while(coinFace === 0){
	console.log("Heads! Flipping again...");
	var coinFace = Math.flo or(Math.random() * 2);
}
console.log("Tails! Done flipping.");

var isTrue = true;
while(isTrue){
	console.log("Hi")
	isTrue =false;)
}

var count = 0;
var loop = function(){
	while(count++ <3){
		console.log("I'm looping!")
	}
};
loop();
```

## do while Loops
```javascript
var loopCondition = false;
do {
	console.log("I'm gonna stop looping 'cause my condition is " + loopCondition + "!");
} while (loopCondition);
```

## Example
```javascript
var slaying = true;
var youHit = Math.floor(Math.random() * 2);
var damageThisRound = Math.floor(Math.random() * 5 + 1);
var totalDamage = 0;

while (slaying) {
	if (youHit) {
		console.log("You hit the dragon and did " + damageThisRound + " damage!");
		totalDamage += damageThisRound;

		if (totalDamage >= 4) {
		  console.log("You did it! You slew the dragon!");
		  slaying = false;
		}
		else {
			youHit = Math.floor(Math.random() * 2);
		}
	}
	else {
		console.log("The dragon burninates you! You're toast.");
		slaying = false;
	}
}
```

# Control Flow
```javascript
/*if else if else*/
var isEven = function(number) {
	if(number %2 === 0){
		return true
	}
	else if((number %2).isNaN()){
		return false;
	}
	else{
		return false;
	}
};

/*for while*/
for(var i =0;i<10; i++){}
while(boolean){}
do{
/*code*/
} while(boolean)

/*switch break*/
var num = parseInt(prompt("input integer")); //string -> integer

switch(num){
    case 1:
    case 2:
        console.log("you chose number 1 or 2");
        break;
    case 3:
        console.log("number 3");
        break;
    default:
        console.log("numbers other than 1,2,3");
        break;
}

/*operator && || !*/
var iLoveJavaScript = true;
var iLoveLearning = true;

if(iLoveJavaScript && iLoveLearning) {
	console.log("Awesome! Let's keep learning!");
} else if(!(iLoveJavaScript || iLoveLearning)) {
	console.log("Let's see if we can change your mind.");
} else {
	console.log("You only like one but not the other? We'll work on it.");
}
```

## Example
```javascript
var troll = prompt("You run into a troll! Do you FIGHT him, PAY him, or RUN?").toUpperCase();

switch(troll) {
	case 'FIGHT':
		var strong = prompt("How courageous! Are you strong (YES or NO)?").toUpperCase();
		var smart = prompt("Are you smart?").toUpperCase();
		if(strong === 'YES' || smart === 'YES') {
			console.log("You only need one of the two! You beat the troll--nice work!");
		} else {
			console.log("You're not strong OR smart? Well, if you were smarter, you probably wouldn't have tried to fight a troll. You lose!");
		}
		break;
	case 'PAY':
		var money = prompt("All right, we'll pay the troll. Do you have any money (YES or NO)?").toUpperCase();
		var dollars = prompt("Is your money in Troll Dollars?").toUpperCase();
		if(money === 'YES' && dollars === 'YES') {
			console.log("Great! You pay the troll and continue on your merry way.");
		} else {
			console.log("Dang! This troll only takes Troll Dollars. You get whomped!");
		}
		break;
	case 'RUN':
		var fast = prompt("Let's book it! Are you fast (YES or NO)?").toUpperCase();
		var headStart = prompt("Did you get a head start?").toUpperCase();
		if(fast === 'YES' || headStart === 'YES') {
			console.log("You got away--barely! You live to stroll through the forest another day.");
		} else {
			console.log("You're not fast and you didn't get a head start? You never had a chance! The troll eats you.");
		}
		break;
	default:
		console.log("I didn't understand your choice. Hit Run and try again, this time picking FIGHT, PAY, or RUN!");
}
```

# Data Structure
```javascript
var arr = ['a', 1, true, new Object()]; //heterogeneous; mixture of data types
console.log(arr[2])
console.log(arr.length)

var arr1 = [[1,2,3],[4,5,6],[7,8,9]] // 2d array
var arr2 = [[1,2,3, true],[4,5,6],[7,8]] //jagged array
var arr3 = [[new Object(), 1, true], [2,"a"]] //jagged array
```

## object
combinations of key-value pairs
```javascript
var myObject = {
    key: value,
    key: value,
    key: value
};
```

```javascript
var phonebookEntry = {};

phonebookEntry.name = 'Oxnard Montalvo'; // name: 'Oxnard Montalvo'
phonebookEntry.number = '(555) 555-5555'; // number: '(555) 555-5555'
phonebookEntry.phone = function() { //phone: function(){}
	console.log('Calling ' + this.name + ' at ' + this.number + '...');
};
phonebookEntry.phone();
```

```javascript
/*object syntax*/
var me = {
    name: "lalala", 
    age: 1 
};

/*create object and initialize*/
var me = new Object(); //var me = {};
me["name"] = "lalala";
me["age"] = 1;

var object1 = new Object();
var object2 = new Object();
var object3 = new Object();
object1["name"] = "object1";
object2["name"] = "object2";
object3["name"] = "object3";
```

```javascript
var myObject = {
	name: 'Eduardo',
	type: 'Most excellent',
	interests: ['reading', 'soccer']
};
```

## Example
```javascript
var friends ={}; // = new Object(); create new object

friends.bill = { // friends["bill"] = {};
	firstName: "Bill",
	lastName: "Gates",
	number: "(206)-000-0000",
	address: ['avenue', 'redmond', 'WA', '90000']
};
friends.steve = { // friends["steve"] = {}:
	firstName: "Steve",
	lastName: "Jobs",
	number: "(408)-000-0000",
	address: ['avenue', 'Cupertino', 'CA', '90000']
};

/*print out keys*/
var list = function(obj){
	for(var prop in obj){
		console.log(prop);
	}
};
var search = function(name){
	for(var prop in friends){
		if(friends[prop].firstName === name){
			console.log(friends[prop]);
			return friends[prop];
		}
	}
};
list(friends);
search("Steve");
```

# Object
each property in an Object has name(key) and value

```javascript
var myObject = {
	key: value, //key(poperty) : value
	key: value,
	key: value
};
```

```javascript
var snoopy = {
	species: "beagle",
	age : 10
};
```

```javascript
var buddy = new Object(); // var buddy = {};
buddy.species = "golden retriever"; // buddy["species"] = "golden retriever"
buddy.age = 5; // budd["age"] = 5;
```

```javascript
var bob = {
	name: "Bob Smith",
	age: 30
};
var susan = {
	name: "Susan Jordan",
	age: 25
};
var name1 = bob.name;
var age1 = bob.age;
var name2 = susan["name"];
var age2 = susan["age"];
```

## Object method
```javascript
var bob = new Object();
bob.age = 17;
bob.name = "Bob Smith";
bob.setAge = function (newAge){
	bob.age = newAge;
	//this.age = newAge;
};
bob.getYearOfBirth = function () {
	return 2014 - bob.age;
};
console.log(bob.getYearOfBirth());
```


```javascript
var setAge = function (newAge) {
	this.age = newAge;
};
var bob = new Object();
bob.age = 30;
bob.setAge = setAge;

// update age
bob.setAge(35)
```

## Constructor
```javascript
function Person(name,age) {
	this.name = name;
	this.age = age;
}
var bob = new Person("Bob Smith", 30);
var susan = new Person("Susan Jordan", 25);
```

## Contructor with methods
```javascript
function Rectangle(height, width) {
	this.height = height;
	this.width = width;
	this.calcArea = function() {
		return this.height * this.width;
	};
	// put our perimeter function here!
	this.calcPerimeter = function(){
		return 2*(height+ width);
	}
}
var rex = new Rectangle(7,3);
var area = rex.calcArea();
var perimeter = rex.calcPerimeter();
```

## Arrays of Objects
```javascript
// Our person constructor
function Person (name, age) {
	this.name = name;
	this.age = age;
}
var family = new Array();
family[0] = new Person("alice", 40);
family[1] = new Person("bob", 42);
family[2] = new Person("michelle", 8);
for(int i =0; i<family.length; i++) console.log(family[i].name);
```

## Object passed into functions
```javascript
// Our person constructor
function Person (name, age) {
	this.name = name;
	this.age = age;
}
var ageDifference = function(person1, person2) {
	return person1.age - person2.age;
}
var olderAge = function(per1, per2){
	if(ageDifference(per1, per2) > 0)
		return per1.age;
	else
		return per2.age;
}
var alice = new Person("Alice", 30);
var billy = new Person("Billy", 25);

var diff = ageDifference(alice, billy);
console.log("older age: " + olderAge(alice, billy));
```

```javascript
function Circle (radius) {
	this.radius = radius;
	this.area = function () {
		return Math.PI * this.radius * this.radius;
	};
	this.perimeter = function(){
		return 2*Math.PI*radius;
	}
};
```

## Example
```javascript
var bob = {
	firstName: "Bob",
	lastName: "Jones",
	phoneNumber: "(650) 777-7777",
	email: "bob.jones@example.com"
};
var mary = {
	firstName: "Mary",
	lastName: "Johnson",
	phoneNumber: "(650) 888-8888",
	email: "mary.johnson@example.com"
};
var contacts = [bob, mary];

function printPerson(person) {
	console.log(person.firstName + " " + person.lastName);
}
function list() {
	var contactsLength = contacts.length;
	for (var i = 0; i < contactsLength; i++) {
		printPerson(contacts[i]);
	}
}
function search(lastName){
	var contactLength = contacts.length;
	for(var i =0;i<contactLength; i++){
		if(contacts[i].lastName === lastName)
			printPerson(contacts[i]);
	}
}
function add(firstName, lastName, email, phoneNumber){
	var contact = new Object();
	contact.firstName = firstName;
	contact.lastName = lastName;
	contact.email = email;
	contact.phoneNumber = phoneNumber;

	contacts[contacts.length] = contact;
}
add("first", "last", "first.last@example.com", "111-1111");
list(contacts)
```

