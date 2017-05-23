* [Values, Types, and Operators](#values-types-and-operators)
* [Program Structure](#program-structure)

# Values, Types, and Operators
basic value types : number, string, boolean, object, function, and undefined value

## Number
```javascript
13;
3.1415;
2.99e11;
```

## Arithmetic
+- * / %
```javascript
(1-2)*10 + 2;
121/10; //12
121%10; //1
```

## Special number
```javascript
Infinity; //special number
-Infinity; 
```

## String
```javascript
"This is a string value\n";
```

## Boolean
```javascript
console.log("Art"<"Science"); //true
```

## Undefined value
```javascript
null;
undefined; //interchangeable with null
```

## Operator
### Unary
```javascript
 //number
console.log(typeof 4.5); console.log(typeof "x"); //number, string
console.log(-(+4)); //-4
```

### Relational
```javascript
console.log(NaN == NaN); //false
console.log(true != false); //true
console.log("Art" < "Science") // → true
console.log(2 >= 1) // → true
```

### Logical
```javascript
console.log(true && false); //false
console.log(true || false); //true
console.log(true ? 1:2); //1 (ternary)
console.log(false ? 1:2); //2
```

## Type conversion
```javascript
console.log(8 * null); // → 0 automatic conversion
console.log("5" - 1); // → 4
console.log("5" + 1); // → 51
console.log("five" * 2); // → NaN
console.log(false == 0); // → true

console.log(null == undefined); // → true
console.log(null == 0); // → false
```

## Short-Circuiting of Logigcal Operators
expression to the right is evaluated only when necessary
```javascript
console.log(null || "user"); // → user
console.log("Karl" || "user"); // → Karl

console.log(true || 0); // → true
console.log(false && 0); // → false
```

# Program Structure

## Variable
```javascript
var one = 1;
var two = 2, three = 3;
console.log(one + two + three);
```

## Keywords and Reserved words
keywords(e.g. var), reserved words(e.g. break case catch class const continue debugger
default delete do else enum export extends false finally for function if implements import in instanceof interface let new null package private
protected public return static super switch this throw true try typeof var void while with yield)

## The Environment
collection of variables and their values that exist at a given time

## Functions
```javascript
alert("Good morning!");
console.log("Hi"); //no pop-up

console.log(Math.min(101, 102) - 100); //return value

confirm("Right?"); //returns true (OK)or false(Cancel)

prompt("Tell us your thoughts.", "...");
```

## Control flow
```javascript
var num = Number(prompt("Type a number", ""));
if (!isNaN(num))
    alert(num " = sqrt(" + num*num + ")");
else
    alert("Input should be a number");
```

## Loop
```javascript
/*while*/
var result = 1;
var count = 0;
while(count < 10){
    result  = result *2;
    count = count + 1;
}
console.log("2^10 = " + result);

/*do while*/
do{
    
} while(){
    
}

/*for*/

```
