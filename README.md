* [Introduction](#introduction-to-javascript)
* [Function](#function)

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

### 