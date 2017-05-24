* [Core JavaScript](#core-javascript)
* [Client-Side JavaScript](#client-side-javascript)
* [Core JavaScript Reference](#core-javascript-reference)
* [Clinet-Side JavaScript Reference](#clinet-side-javascript-reference)

# Core JavaScript

## Lexical structure
set of elementary rules that specifies how you write programs in that language;
lowest-level syntax of a language

```javascript
/*Literals*/
20
3.14
"Hi"
true
false
/javascript/gi //regular expression literal(pattern matching)
undefined
null //absence of an object

/*Object and array literals*/
{x:1, y:2} //an object initializer
[1, 2, 3] //an array initializer

/*Identifier to name variables and functions and to provide labels for certain loops
allows to contain letters and digits from the entire Unicode character set*/
i
my_num
_dummy
$str
var sí = true;
var π = 3.14; //pi

/*Reserved Words
break delete function return typeof case do if switch var catch else in this void 
continue false instanceof throw while debugger finally new true with default for null try */

/*Optional semicolons*/
a=3;
b=4;

var a  //interpreted as: var a;
a=3 //a=3;
console.log(a) //console.log(a);

var y = x + f
(a+b).toString() //var y= x + f(a+b).toString();

var x=0
;[x,x+1,x+2].forEach(console.log) //defensive semicolon to separate statement from above

return
true;  //return; true;

x
++
y  //x; ++y;
```

## Types, Values, and Variables

### Numbers
```javascript
/*Integer Literals*/
255 //base 10
0xfff //hexadecimal; 15*16^1 + 15 = 255
0377 //octal; 3*8^2 + 7*8^1 = 255

/*Floating-Point Literals*/
3.1415
.3333333
6.02e23 // 6.02 × 10^23
1.4738223E-32 // 1.4738223 × 10^−32

/*Arithmetic*/
Math.pow(2,10) // Math library

/*overflow, underflow, or division by zero.*/
Infinity // A read/write variable initialized to Infinity.
Number.POSITIVE_INFINITY // Same value, read-only.
1/0 // This is also the same value.
Number.MAX_VALUE + 1 // This also evaluates to Infinity.

Number.NEGATIVE_INFINITY // These expressions are negative infinity.
-Infinity
-1/0
-Number.MAX_VALUE - 1

NaN // A read/write variable initialized to NaN.
Number.NaN // A read-only property holding the same value.
0/0 // Evaluates to NaN.

Number.MIN_VALUE/2 // Underflow: evaluates to 0
-Number.MIN_VALUE/2 // Negative zero
-1/Infinity // Also negative 0
-0

var zero = 0; // Regular zero
var negz = -0; // Negative zero
zero === negz // => true: zero and negative zero are equal
1/zero === 1/negz // => false: infinity and -infinity are not equal

/*Binary Floating-Point and Rounding Errors*/
var x = .3 - .2; // thirty cents minus 20 cents
var y = .2 - .1; // twenty cents minus 10 cents
x == y // => false: the two values are not the same!
x == .1 // => false: .3-.2 is not equal to .1
y == .1 // => true: .2-.1 is equal to .1

/*Dates and Times*/
var then = new Date(2010, 0, 1); // The 1st day of the 1st month of 2010
var later = new Date(2010, 0, 1, 17, 10, 30);// Same day, at 5:10:30pm, local time
var now = new Date(); // The current date and time
var elapsed = now - then; // Date subtraction: interval in milliseconds
later.getFullYear() // => 2010
later.getMonth() // => 0: zero-based months
later.getDate() // => 1: one-based days
later.getDay() // => 5: day of week. 0 is Sunday 5 is Friday.
```

### Text
A string is an immutable orderd sequence of 16-bit values

```javascript
/*String Literals*/
"" // The empty string: it has zero characters
'testing'
"3.14"
'name="myform"'
"Wouldn't you prefer O'Reilly's book?"
"This string\nhas two lines"
"π is the ratio of a circle's circumference to its diameter"

"two\nlines" // A string representing 2 lines written on one line
"one\ 
long\
line" // A one-line string written on 3 lines. ECMAScript 5 only.

/*Escape Sequence*/
'You\'re right, it can\'t be a quote'

\0 The NUL character ( \u0000 )
\b Backspace ( \u0008 )
\t Horizontal tab ( \u0009 )
\n Newline ( \u000A )
\v Vertical tab ( \u000B )
\f Form feed ( \u000C )
\r Carriage return ( \u000D )
\" Double quote ( \u0022 )
\' Apostrophe or single quote ( \u0027 )
\\ Backslash ( \u005C )
\x XX The Latin-1 character specified by the two hexadecimal digits XX
\u XXXX The Unicode character specified by the four hexadecimal digits XXXX
"café" === "caf\u00e9"; // => true

/*Working with Strings*/
var msg = "Hello, " + "world"; // Produces the string "Hello, world"
var greeting = "Welcome to my blog," + " " + name;

var s = "hello, world" // Start with some text.
s.length //length of the string
s.charAt(0) // => "h": the first character.
s.charAt(s.length-1) // => "d": the last character.
s.substring(1,4) // => "ell": the 2nd, 3rd and 4th characters.
s.slice(1,4) // => "ell": same thing
s.slice(-3) // => "rld": last 3 characters
s.indexOf("l") // => 2: position of first letter l.
s.lastIndexOf("l") // => 10: position of last letter l.
s.indexOf("l", 3) // => 3: position of first "l" at or after 3
s.split(", ") // => ["hello", "world"] split into substrings
s.replace("h", "H") // => "Hello, world": replaces all instances
s.toUpperCase() // => "HELLO, WORLD"

s = "hello, world";
s[0] // => "h"
s[s.length-1] // => "d"

/*Pattern Matching
JavaScript defines a RegExp() constructor for creating objects that represent textual patterns.
These patterns are described with regular expressions, and JavaScript adopts Perl’s syntax 
for regular expressions. RegExps are powerful and commonly used for text processing */
/^HTML/ // Match the letters H T M L at the start of a string
/[1-9][0-9]*/ // Match a non-zero digit, followed by any # of digits
/\bjavascript\b/i // Match "javascript" as a word, case-insensitive

/*RegExp objects define a number of useful methods, and strings also have methods that
accept RegExp arguments. For example:*/
var text = "testing: 1, 2, 3"; // Sample text
var pattern = /\d+/g // Matches all instances of one or more digits
pattern.test(text) // => true: a match exists
text.search(pattern) // => 9: position of first match
text.match(pattern) // => ["1", "2", "3"]: array of all matches
text.replace(pattern, "#"); // => "testing: #, #, #"
text.split(/\D+/); // => ["","1","2","3"]: split on non-digits
```

### Boolean Values
```javascript
true
false
/*All JavaScript values, including all objects (and arrays) work like, true
except for the following that works like false :*/
undefined
null
0
-0
NaN
"" // the empty string

if ((x == 0 && y == 0) || !(z == 0)) {
    // x and y are both zero or z is non-zero
}
```

### null and undefined
```javascript
null //keyword
undefined //absence of value; predefined global value
typeof null //object
typeof undefined //undefined
null == undefined //true
null === undefined //false
```

### The Global Object
* global properties like undefined , Infinity , and NaN
* global functions like isNaN() , parseInt() (§3.8.2), and eval() (§4.12).
* constructor functions like Date() , RegExp() , String() , Object() , and Array()
* global objects like Math and JSON

### Wrapper Objects
```javascript
var s = "hello world!"; // = new String("hello world!");
var word = s.substring(s.indexOf(" ")+1, s.length); // Use string properties
var num = 1; //Number()
var isTrue = true; //Boolean()

var s = "test";
s.len = 4; //create temporary String object(Wrapper object), set len =4, and discard it
var t = s.len; //undefined, since len property does not exist in String object

/*Note that it is possible (but almost never necessary or useful) to explicitly create wrap-
per objects, by invoking the String() , Number() , or Boolean() constructors:*/
var s = "test", n = 1, b = true; // A string, number, and boolean value.
var S = new String(s); // A String object
var N = new Number(n); // A Number object
var B = new Boolean(b); // A Boolean object
```

### Immutable Primitive Values and Mutable Object Reference
PRIMITIVE VALUES (undefined, null , booleans, numbers, and strings) are immutable and 
compared by values
```javascript
var s = "hello"; // Start with some lowercase text
s.toUpperCase(); // Returns "HELLO", but doesn't alter s
s // => "hello": the original string has not changed

var s1 = "hello";
var s2 = "hello";
s1 === s2; //true
```

OBJECTS (including arrays and functions) is mutable, and not compared by value
```javascript
var o = { x:1 }; // Start with an object
o.x = 2; // Mutate it by changing the value of a property
o.y = 3; // Mutate it again by adding a new property
var a = [1,2,3] // Arrays are also mutable
a[0] = 0; // Change the value of an array element
a[3] = 4; // Add a new array element

/*two obejcts are not equal even if they have the same properties and values*/
var o = {x:1}, p = {x:1}; // Two objects with the same properties
o === p // => false: distinct objects are never equal
var a = [], b = []; // Two distinct, empty arrays
a === b // => false: distinct arrays are never equal
```

Objects are called reference types to distinguish them from primitive types;
object values are references, and we say that objects are compared by reference: 
two object values are the same if and only if they refer to the same underlying object.
```javascript
var a = []; // The variable a refers to an empty array.
var b = a; // Now b refers to the same array.
b[0] = 1; // Mutate the array referred to by variable b.
a[0] // => 1: the change is also visible through variable a.
a === b // => true: a and b refer to the same object, so they are equal.
```

To avoid this, and create a new copy of an object(or array):
```javascript
var a = ['a','b','c']; // An array we want to copy
var b = []; // A distinct array we'll copy into
for(var i = 0; i < a.length; i++) { // For each index of a[]
    b[i] = a[i]; // Copy an element of a into b
}
```

Since objects(arrays) can be different even if they have exact same properties and elements, 
one has to define a method to avoid this:
```javascript
function equalArrays(a,b) {
    if (a.length != b.length) return false; // Different-size arrays not equal
    for(var i = 0; i < a.length; i++) // Loop through all elements
        if (a[i] !== b[i]) return false; // If any differ, arrays not equal
    return true; // Otherwise they are equal
}
```

### Type Conversions
refer to page 46
```javascript
10 + " objects" // => "10 objects". Number 10 converts to a string
"7" * "4" // => 28: both strings convert to numbers
var n = 1 - "x"; // => NaN: string "x" can't convert to a number
n + " objects" // => "NaN objects": NaN converts to string "NaN"
```

### Conversions and Equality
```javascript
null == undefined // These two values are treated as equal.
"0" == 0 // String converts to a number before comparing.
0 == false // Boolean converts to number before comparing.
"0" == false // Both operands convert to numbers before comparing
```

### Explicit Conversions
```javascript
Number("3") // => 3
String(false) // => "false" Or use false.toString()
Boolean([]) // => true
Object(3) // => new Number(3)

/*Implicit Conversions*/
x + "" // Same as String(x)
+x // Same as Number(x). You may also see x-0
!!x // Same as Boolean(x). Note double !
```