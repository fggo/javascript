* [Values, Types, and Operators](#values-types-and-operators)
* [Program Structure](#program-structure)

# Values, Types, and Operators
js basic value types : number, string, boolean, object, function, and undefined value

## Number and Arithmetic
13 3.1415 2.99e11 
```javascript
(1-2) *10
121%11 //0
111%10 //1
Infinity //special number
-Infinity 
```

## String
```javascript
var str = "This is a string variable\n"
```

## Unary operator
```javascript
console.log(typeof 4.5) //number
console.log(typeof "x") //string
console.log(-(0-1)) //1
```

## Boolean
```javascript
console.log("Art"<"Science") //true
```

## Comparison
```javascript
console.log(NaN == NaN) //false
console.log(true && false) //false
console.log(true || false) //true
console.log(true != false) //true
console.log(true ? 1:2) //1 (ternary operator)
console.log(false ? 1:2) //2
```

## Undefined value
```javascript
null
undefined //interchangeable with null
```

## Automatic type conversion
```javascript
console.log(8 * null) // → 0
console.log("5" - 1) // → 4
console.log("5" + 1) // → 51
console.log("five" * 2) // → NaN
console.log(false == 0) // → true

console.log(null == undefined); // → true
console.log(null == 0); // → false
```

## Short-Circuiting of Logigcal Operators
expression to the right is evaluated only when necessary

```javascript
console.log(null || "user") // → user
console.log("Karl" || "user") // → Karl

console.log(true || 0) // → true
console.log(false && 0) // → false
```

# Program Structure