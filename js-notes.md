Notes on Javascript:

///////////////////////////////////////////////////////////
3/16/23

// Comments start after double slash

1. Values: smallest unit of information in JS, can be stored into variables to be reused.

- Every value is an object or primitative.

2. Variables: 'named storage' for data. Variables are used to store data.

- let and const

- const is permanent

- Variables are named using camel case (camelCase) when more than one word.

- Variables cannot start with a number, and can only contain letters, numbers, underscores, or $

- Reserves keywords cannot be used for variables(unless starting with \_ or $)

- Use descriptive names for variables (easy to understand)

  - let myFirstJob = 'Programmer';
    let myCurrentJob = 'Teacher';

  let job1 = 'programmer';
  let job2 = 'teacher';

3. Data Types:

- 7 Primitative Types:

  1. Numbers: floating point numbers, used for decimals and integers.

  - let age = 23;

  2. Strings: sequence of characters, used for text. Always put them in quotes. Single or double '', ""

  - let firstName = 'Morlando';

  3. Boolean: Logical type that can only be true or false, used for decision making.

  - let fullAge = true;
  - Booleans can be stored in variables.
    - let javascriptIsFun = true;
      console.log(javascriptIsFun);

  4. Undefined: Value take by a variable that is not yet defineded ('empty value')

  - let children;

  5. Null: Also means empty value

  6. Symbol: Value that is unique and cannot be changed.

  7. BigInt: Larger integers than the number tyle can hold.

- Data types are determined automatically with JavaScript. We do not need to manually define the data type of the value stored in a variable

4. Three ways to declare variables:

- let, const, var, let and const were added in ES6
- let is used to declare variables that can be changed later.
  - let age = 30;
    age = 31;
- const is used to declare variables that are not supposed to change in the future. Const values cannot be changed.
  - const birthYear = 1991;
    birthYear = 1990;
    - Will produce a TypeError
- var should be completely avoided, used for legacy reasons
  - old way of declaring variables, works similar to let
  - var job = 'programmer';
    job = 'teacher';
  - never use var

5. Operators:

- assignment x = f()
- addition x += f()
- subtraction x-= f()
- multiplication x \*= f()
- division x /= f()
- remainder(modulo) x %= f()
- exponentiation x \*\*= f()
- comparison operators:
  - // >, <, >=, <=

6. Operator Precident:

- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Pregicedence#table

////////////////////////////////////////////////////////////////////
3/20/23

7. Falsy and Truthy Values

- Five falsy values: , '', undefined, null, NaN

  - All five values will be converted to false when converted to a Boolean

- Truthy values: values that will be converted to true
- ie: any number, any string that is not an empty string
- Truthy and Falsy values can be used to check if a variable is defined
  - let height;
    if (height) {
    console.log("Yay! Height is defined"); // falsy as height is undefined
    } else {
    console.log("Height is undefined");
    }

8. Equality Operators

- Checks whether both operands are equal.
- Operator will return Boolean value
- Equality(==): Transforms operands having the same type before comparison.
  - ie: '18' == 18; true, string is converted to a number.
- Strict equality (===): does not perform type coercision, will only return true if both values are the same
- '18' === 18; false, does not perform type coercision

- Example:
  const favorite = prompt("What's your favorite number?");
  console.log(favorite);
  console.log(typeof favorite); // answer converted to a string

  if (favorite == 23) {
  // Type coercision performed to turn to a number '23' == 23
  console.log("Cool, 23 is an amazing number");
  }

  if (favorite === 23) {
  // Strict equality, type coercison not performed
  console.log("Cool, 23 is an amazing number");
  }

- Inequality (!=): checks whether its two operands are not equal, returns boolean value.
  - Attemps to convert and compare operands that are of different types.
  - x != y; !(x == y);
    - 1 != 1; false
    - 1 != 2; true
    - 0 != false; false
    - 0 != null; true
- Strict inequality (!==): checks whether its two operands are not equal, returns boolean value.
  - Always considers operands of different types to be different
  - x !== y; !(x === y);
    - 1 !== 1; false
    - '1' !== 1; true
    - 0 !== false; true
    - null !=== undefined; true

9. Boolean Logic: And, Or, Not Operators (&&, ||, !)

- &&: When we use the && operator, we are checking that two things are true
  - if (stopLight === 'green' && pedestrians === 0) {
    console.log('Go!');
    } else {
    console.log('Stop');
    }
- ||: If we only care about either condition being true, we can use the || operator
  - if (day === 'Saturday' || day === 'Sunday') {
    console.log('Enjoy the weekend!');
    } else {
    console.log('Do some work.');
    }
- !: The ! not operator reverses, or negates, the value of a boolean

  - let excited = true;
    console.log(!excited); // Prints false
  - let sleepy = false;
    console.log(!sleepy); // Prints true

- const hasDriversLicense = true; // A
  const hasGoodVision = true; // B
  const isTired = false; // C

  if (hasDriversLicense && hasGoodVision && !isTired) {
  console.log("Sarah is able to drive"); // returns this block of code
  } else {
  console.log("Someone else should drive...");
  }

10. Switch Statements

- Evaluates an expression, matching the expression's value against a series of case clauses, and executes statements after the first case clause with a matching value, until a break statement is encountered.

  - switch (expression) {
    case value1:
    // Statements of executed when the
    // result of expression matches value1
    [break;]
    case value2:
    // Statements executed when the
    // result of expression matches value2
    [break;]
    case valueN:
    // Statement executed when the
    // result of expression matches valueN
    [break;]
    [default:
    // Statements executed when none of
    // the values match the value of the expression
    [break;]]
    }

    - Example:
      // const day = "monday";

    // switch (day) {
    // case "monday": // day === monday
    // console.log("Plan course structure");
    // console.log("Go to coding meet up");
    // break;
    // case "tuesday":
    // console.log("Preparing theory videos");
    // break;
    // case "wednesday":
    // case "thursday":
    // console.log("Write code examples");
    // break;
    // case "friday":
    // console.log("Record videos");
    // break;
    // case "saturday":
    // case "sunday":
    // console.log("Enjoy the weekend");
    // break;
    // default:
    // console.log("Not a valid day");
    // }

- Without the break the code will continue to execute. The break informs the code to stop.
- Alternative to writing the following example:
  // if (day === "monday") {
  // console.log("Plan course structure");
  // console.log("Go to coding meet up");
  // } else if (day === "tuesday") {
  // console.log("Preparing theory videos");
  // } else if (day === "wednesday" || "thursday") {
  // console.log("Write code examples");
  // } else if (day === "friday") {
  // console.log("Record videos");
  // } else if (day === "saturday" || "sunday") {
  // console.log("Enjoy the weekend");
  // } else {
  // console.log("Not a valid day");
  // }

11. Statements and Expressions

- Statements are larger pieces of codes that are executed and do not produce a value itself.
  - if (23>10) {
    const str = '23 is bigger';
    }
- Expression: piece of code that produces a value, i.e: 3 + 4, 1991

  - the string in the example above is an expression.

- JS expects statments and expressions in different places
  - Template literals can only insert expressions and not statements
    - console.log(`${EXPRESSION}`)

12. The Conditional Operator

- Also called Ternary operator
  - Has 3 parts: Condition, if, else
- Similar to if else statement but in one line
  - const age = 23;
    age >= 18 ? console.log('I like to drink wine') : console.log('I like to drink water');
  - const drink = age >= 18 ? "wine" : "water";
    console.log(drink);
  - console.log(`I like to drink ${age >= 18 ? "wine" : "water"}`); // Can be used w/ template literals
  - Compared to:
    let drink2;
    if (age >= 18) {
    drink2 = "wine";
    } else {
    drink2 = "water";
    }
    console.log(drink2);
- Not a full replacement for if/else statements

///////////////////////////////////////////////////////////////////////////////

3/21/23

13. Functions

- A function is a piece of program wrapped in a value. Such values can be applied in order to run the wrapped program.
- Fundamental building block of JavaScript
- Executing a function is called invoking, calling, running or applying.
- A function can be called by putting parantheses() after an expression that produces a function value.
- The values between the parantheses are given to the program inside the function.
- Values given to the function are called arguments.
- When a function produces a value, it is said to return that value.
  - Anything that produces a value is an expression is JavaScript.
- Examples:
  - Function declaration: Function that can be used before it's declared.
    // function calcAge(birthYear) {
    // return 2037 - birthYear;
    // }
  - Function expressions: Function value stored in a variable
    // const calcAge = function (birthYear) {
    // return 2037 - birthYear;
    // };
  - Arrow Function: Great for a quick one line function.
    // const calcAge = birthYear => 2037 - birthYear;
  - Three different ways of writing functions ut all work in similar way
    - Receive input data, transform data, and then output data.
- Function Structure:
  // function calcAge(birthYear, firstName) {
  // const age = 2037 - birthYear;
  // console.log(`${firstName} is ${age} years old.`);
  // return age;
  // }
  const age = calcAge(1991, 'Bob');
  - Function name:
    // (calcAge)
  - Parameter: Placeholder to receive input values. Like local variables of a function.
    // (birthYear, firstName)
  - Function body: Block of code that we want to reuse. Processes the function's input data.
    // const age = 2037 - birthYear;
    // console.log(`${firstName} is ${age} years old.`);
  - Return: Statement to output a value from the function and terminate execution.
    // return age;
  - Calling, running, invoking, using ()
  - Arguments: actual values of function parameters, to input data
    // (1991, 'Bob');

///////////////////////////////////////////////////////////////////////////////
3/22/23

14. Arrays and Objects

- Data type specifically for storing sequences of values.
- Written as a list of values between square brackets, separated by commas.
  - let listOfNumbers = [2, 3, 5, 7, 11];
- The first index of an array is zero. i.e listofNumbers[0]; will produce the number 2.
- Methods (Operations):

  - There are a vast length of methods in JavaScript.
  - The following are common basic methods: - Push: add elements at the end of an array. - const fiends = ['Michael', 'Steven', 'Peter']; - friends.push('Jay'); - Unshift: add element at the beginning of an array. - friends.unshift('John');
    -Pop: will remove last element of array.
    - friends.pop();
    - Shift: remove element at beginning of an array.
      - friends.shift();
    - IndexOf: used to search for a specific value.
      - console.log(friends.indexOf('Steven'));
    - Includes: will return true if in array, false if not.
      - console.log(friends.includes('Steven')); // true
      - console.log(friends.includes('Bob')); // false
      - Uses strict equality to check array, can be used in conditionals to test.
      - if (friends.includes("Steven")) {
        console.log("You have a friend named Steven");
        }

- Objects allow us to group values, including other objects, to build more complex structures.

  const morlando = {
  firstName: "Morlando",
  lastName: "Johnson",
  age: 2023 - 1985,
  job: "insurance",
  friends: ["Bob", "Pete", "Carl"],
  };
  console.log(morlando);

console.log(morlando.lastName);
console.log(morlando["lastName"]);

const nameKey = "Name";
console.log(morlando["first" + nameKey]);
console.log(morlando["last" + nameKey]);

const interestedIn = prompt(
"What do you want to know about Morlando? Choose between firstName, lastName, age, job, and friends"
);

if (morlando[interestedIn]) {
console.log(morlando[interestedIn]);
} else {
console.log(
"Wrong request! What do you want to know about Morlando? Choose between firstName, lastName, age, job, and friends"
);
}

morlando.location = "Florida";
morlando["github"] = "Lando241";
console.log(morlando);

// Challenge
// "Morlando has 3 friends and his best friend is Bob"

console.log(
`${morlando.firstName} has ${morlando.friends.length} friends and his best friend is ${morlando.friends[0]}`
);

15. Loops

- Fundamental Aspect of every programming language
- Help to automate tasks that need to be performed over and over again.
- For Loops:
  for (let number = 0; number <= 12; number +2) {console.log(number);
  }
  // - 0
  // - 2
  // - etcetera
  - For loop continues to run while condition is true.
  - Parantheses after a for keyword must contain two semicolons.
    - The part before the first semicolon initializes the loop, usually by defining a binding.
    - The second part is the expression that checks whether the loop must continue.
    - The final part updates the state of the loop after every interaction.
  - 'i' is the traditional letter for for loops
    - for(let i = 0)
- Breaking out of a loop

  - There is a special statement called break that has the effect of immediately jumping out of the enclosed loop.
    - for (let current = 20; ;current = current +1) {
      if (current % 7 == 0){
      console.log(current);
      break;
      }
      }
      // 21
    - Modulo is an easy way to test whether a number is divisible by another number(remainder is 0)
    - Example above doesn't check for end of loop, which means the loop will not stop with the break.
    - Infinite loop would be produced if break statement was not included, programs stuck in an infinite loop will never finish running.
  - Continue is similar to break, when encountered in a loop, control jumps out of the body and continues with the loop's next interation.

- While Loops:

  - while is followed by an expression in parentheses and then a statement, much like if.
  - The loop keeps entering that statemnet as long as the expression produces a value that gives true when converted to a boolean.
  - Example:
    let rep = 1;
    while (rep <= 10) {
    console.log(`Lifting weights repetition ${rep}.`)
    rep++;
    }
  - Example: (Dice Roll)
    let dice = Math.trunc(Math.random() \* 6 + 1);

    while (dice !== 6) {
    console.log(`You rolled a ${dice}`);
    dice = Math.trunc(Math.random() \* 6 + 1);
    if (dice === 6) console.log("Loop is about to end");
    }

///////////////////////////////////////////////////////////////////////////////
3/23/23

1. DOM and DOM Manipulation

- Document Object Model, structured representation of HTML documents.
  - Change text, HTML attributes, CSS styles
- Automatically created by browser once HTML page loads
- Stored in a tree structure
  - Each HTML element is one object
- Allows JS to access HTML elements and styles to manipulate them.
- DOM always starts with document object at the top
  - Document object serves as an entry point to the DOM (i.e: document.querySelector();), needed to select elements
  - First child of document is usually HTML element (root element)
  - HTML usually has 2 child elements, <head></head> and <body></body>
    - These elements are siblings as they are adjacent elements.
  - DOM !== JavaScript, not part of JS language
  - DOM methods and properties are part of WEB APIs (libraries for browsers)
    - API: Application Programming Interface
  - DOM manipulation works the same in all browsers.

//////////////////////
Minimal notes for today. Installed node.js, introduction to the DOM, created tutorial project.

///////////////////////////////////////////////////////////////////////////////
3/24/23

1. Modal Tutorial from Udemy Course

The Complete JavaScript Course 2023: From Zero to Expert! by Jonas Schmedtmann

Using JS to open and close a modal window.
Learning how to store elements as variables in JS. Doing so will help to avoid having to select various elements over and over.

Examples from tutorial:

const modal = document.querySelector('.modal');
const overlay = document.querySelector('.overlay');
const btnCloseModal = document.querySelector('.close-modal');
const btnsOpenModal = document.querySelectorAll('.show-modal');

Learning how to create functions to help avoid duplicating code

- Function to open modal windows as well as closing them.
- Doing so helped to eliminate duplicating close in multiple places.

Learning how to work with CSS classes

- Adding and removing classes to activate and decactive the CSS code (showing and closing the modal window)
- Classes can also be checked using JS to determine if they contain a specific class
- Tutorial example is using boolean logic to determine if the modal does not contain the 'hidden' element, if it does not then the keystroke on ESC is used to close the modal window.
  - document.addEventListener('keydown', function (event) {
    if (event.key === 'Escape' && !modal.classList.contains('hidden')) {
    closeModal();
    }
    });

///////////////////////////////////////////////////////////////////////////////
3/28/23

Closer look at functions from Javascript.info and MDN.
I've been having trouble w/ functions over the past few days. I understand how they work but I think I'm getting confused by the syntax of arguments, parameters, types of functions and when to use them to avoid duplcating code.

1. Function Declaration:

- defines the function with speficied parameters.

function name(parameter1, parameter2, parameterN) {
//body
}

function showMessage(){
alert('Hello everyone!');
}

- function keyword goes first, then name of the function, then a list of parameters between the parantheses, followed by the code of the function "function body" between the curly braces.
- function can be called by its name, i.e showMessage();
- Calling the function executes the codes of the function.
- Functions help to avoid code duplication.

2. Variables, local and outer.

- A variable declared inside a function is only visible inside that function.
- Variables declared outside a function are called global variables.
- Global variables are visible from any function.

function showMessage() {
let message = 'Hello, I'm JavaScript';
alert(message);
}

show message(); //Hello, I'm JavaScript
alert(message); // <- Will produce error message

- Functions can access an outer variable as well and can modify it

let userName = 'John';

function showMessage() {
let message = 'Hello, ' + userName";
alert(message);
}

showMessage(); // Hello John

let userName = 'John';

function showMessage() {
userName = 'Bob';
let message = 'Hello, ' + userName";
alert(message);
}
alert(userName); // John
showMessage(); // Hello John
alert(userName); // Bob, changed by function

3. Parameters

- Named variable passed into a function, used to import arguments into functions.
- Parameters are the variables listed within the parantheses of the function declaration

- When the function is called, the given values(arguments) are copied to the parameters within the function declaration and used by the function

function showMessage(from, text) { // parameters: from, text
alert(from + ': ' + text);
}

showMessage('Ann', 'Hello!'); // Ann: Hello! (\*)
showMessage('Ann', "What's up?"); // Ann: What's up? (\*\*)

4. Arguments

- Value that is passed as input(function parameter) to a function when the function is called.

showMessage(argument1, argument2);

5. Returning a value

- When a return statement is used in a function body, the execution of the function is stopped.
- If specified, a given value is returned to the function caller.
- Syntax:
  reutrn;
  return expression;

function sum(a, b) {
return a + b;
}
let result = sum(1, 2)
alert(result); //3

6. Function Expression

- Allows for creation of a new function in the middle of any expression.
- Function creation happens in the context of the assignment expression (to the right side of =)
- Example:

let sayHi = function() {
alert('Hello');
}

- Omitting a name is allowed for function expressions(no name after function)

7. Function Expression v. Function Declaration

- Function Declaration: a function, declared as a separate statement, in the main code flow

function sum(a, b) {
return a + b;
}

- Function Expression: a function, created inside an expression or inside another syntax construct.

let sum = function(a, b) {
return a + b;
}

- A Function Expression is created when the execution reaches it and is usable only from that moment.

- A Function Declaration can be called earlier than it is declared.

- In strict mode, when a Function Declaration is within a code block, it's visible everywhere inside that block. But not outside of it.

let age = 16;

if (age < 18) {
welcome();

function welcome() {
alert('Hello');
}
welcome();
} else {
function welcome() {
alert('Greetings');
}
}

welcome(); // Welcome is undefined, Function declaration is available everywhere in the block where it was declared

8. Arrow Functions

- Shorter alternative to function expression.
- Syntax:
  () => expression

param => expression

(param) => expression

(param1, paramN) => expression

() => {
statements
}

param => {
statements
}

(param1, paramN) => {
statements
}

- Example:
  let sum = (a, b) => a + b;
  console.log(sum(1, 2));

Same as:
let sum = function(a, b) {
reutrn a + b;
}
console.log(sum(1, 2));

///////////////////////////////////////////////////////////////////////////////
3/29/23

1. Global Execution Context created for top level code

- Code not inside any function
- Functions can be declared to be called later but the code in the function is only executed when called

Execution context - environment where JS is executed (like a box).
There is only one global execution context

- Default context, created for code that is not inside any function (top-level)

For each function call, a new execution context is created containing all the information to run that function. Same for methods(functions attached to objects).

2. All these executions contexts make up the Call Stack.

- Once all functions are done executing, the JS engine waits for callbacks to arrive.
- Click event, etc

3. Inside an execution context:

- Variable environment: all variable and function declarations are stored.
- Arguments objects: all arguments passed into the function that the current execution context belongs to. (Each function gets its own execution context).
  -Functions can also access variables outside the function.
  - Arrow functions do not get their own arguments object or this keyword.
    - Obtain from function parent.
- Scope Chain
- this keyword

4. Call Stack

- Place where execution contexts are stacked on top of each other to keep track of where we are in the execution.
- Context is put on top of the call stack aftering being executed, next context is then called and stacked on top after execution.

5. Scoping

- How our program's variables are organized and accessed.
- Lexical Scoping: Scoping is controlled by placement of functions and blocks in code.
  - For example, a function that is written inside another fucntion has access to variables of parent function.
- Scope: Space or environment in which a certain variable is declared(variable environment in case of functions). There is global scope, fucntion scope, and block scope.

  - Scope of variable is the entire region where a variable can be accessed.

- 3 Types of Scope: Global, Function, Block
  - Global:
    - Outside of any function or block
    - Variables declared in global scope are accessible everywhere
  - Function:
    - Variables are accessible only inside function, NOT outside.
    - Also called local scope.
  - Block
    - Variables are accesible only inside block(block scoped).
    - However, this only applies to let and const variables.
    - Functions are also block scoped(only in strict mode-always use strict mode).
- Every scope always has access to all the variables from all its outer scopes(parent scopes).

const myName = '';

function first() {
const age = 30;

if (age >= 30) {
const decade = 3;
var millenial = true;
}
function second() {
const job = 'teacher';
console.log(`${myName} is a ${age}-old ${job}`)
}

second();
}

first();

- In the example above the scopes are as followed:
  - Global scope: (myName = '')
  - first() scope: (age = 30), myName = '', millenial = true
  - second() scope: job = 'teacher', age = 30, myName = '', millenial = true
- Scope has access to variables from all outer scopes.
- This shows how a scope chain works, if one scope needs to use a variable and cannot find it in the current scope, it will look in the scope chain to find the variable in a parent scope.
  - If it cannot find the variable, it will produce an error
  - Process is called variable lookup.
  - Variables are not copied from one to another, they simply look up to find the variable.
  - This process does not work in reverse (look down).
    - First scope cannot access the job variable in the second scope.
- Blocks also create scopes, above(between {})
  - var variable does not apply to block scope, only let and const
  - Block scope does not get access to any variables in second scope and vice versa in example above.
    - Because of lexical scoping - because they are not written inside the other., Chain only works upwards, not sideways.

6. Scope Chain v. Call Stack

- Variables stored in the Global scope are the same variables stored in the Global Execution Context
- Scope Chain has nothing to do with order in which functions were called(Nothing to do w/ execution contexts in Call stack).

7. Recap:

- Scoping asks the question, "where do variables live/where can we access a certain variable, and where not?
- 3 types of scopes
  - Global, function, block(ES6).
    - Only let and const are block-scoped.
    - var ends up in the closest function scope.
- Lexical Scoping
  - Rules of where we can access variables are based on exactly where in the code functions and blocks are written.
- Every scope has access to all the variables from its outer scope, Scope Chain
- JS Engine will look up in the scope chain to find the variable it is looking for. (Variable lookup)
  - Scope chain cannot look downward(children/inner scopes)
- Scope chain is equal to adding together all variable environments of all parent scopes.
- Scope chain has nothing to do with the order in which functions were called.

8. Hoisting

- Makes some types of variables accessible/usable in the code before they are actually declared. "Variables lifted to the top of their scope."
  - Before execution, code is scanned for variable declarations, and for each variable, a new property is created in the variable environment object.
- Temporal Dead Zone(TDZ)

  - let and const
  - Variable has not been initialized with a value, and any attempt to access it will result in a ReferenceError
  - The variable is initialized with a value when execution reaches the line of code where it was declared.
    - If no initial value was specified with the variable declaration, it will be initialized with a value of undefined.
  - Introduced in ES6, this process is easier to avoid and catch errors
  - Makes const variables work, cannot be set to undefined first and then reassigned. Only assigned when execution reaches declaration.

- Being able to use a variable's value in its scope before the line it is declared('Value hoisting')
- Being able to reference a variable in its scope before the line it is declared.
  - Value is always undefined.

9. The 'this' keyword

- Special variable that is created for every execution context(every function). Takes the value of (points to) the 'owner' of the function in which the this keyword is used.
- value is not static. It depends on how the function is called, and its value is only assigned when the function is actually called.

Method -> this = <object that is calling the method>
Example:

const jonas = {
name: 'Jonas',
year: 1989,
calcAge: function() {
return 2037 - this.year;
}
};
jonas.calcAge(); // 48

- In the example above the method is calcAge because it is a function attached to the jonas object.
- The value of the 'this' keyword is jonas, because it is the object that is calling the method.
- jonas.year is the same as this.year

Simple function call -> this = undefined (strict mode only)

Arrow functions -> this = <this of surrounding function(lexical 'this')>

Event listener -> this = <DOM element that the handler is attached to>

- 'this' does not point to the function itself and also not the varible environment

'this' keyword example:

const jonas = {
year: 1991,
calcAge: function () {
console.log(this);
console.log(2037 - this.year);
},
};
jonas.calcAge(); // this keyword is the jonas object, line 91

const matilda = {
year: 2017,
};

matilda.calcAge = jonas.calcAge;
matilda.calcAge();

this keyword always points to the object calling the method in this example we are calling the method on matilda. So this keyword will point ot matilda even though the method is written inside the jonas Object.

Arrow function 'this' example:

const jonas = {
firstName: 'Jonas',
year: 1991,
calcAge: function () {
console.log(this);
console.log(2037 - this.year);
},

greet: () => console.log(`Hey ${this.firstName}`),
};
jonas.greet();

- this will produce Hey undefined. The arrow function does not get its own this keyword. So the this keyword is going off the parent, which is the global scope(the window, where firstName is not defined.)

///////////////////////////////////////////////////////////////////////////////
4/2/23

Eloquent JavaScript, Chapter 2: Program Structure

1. Expressions and Statements:

- A fragment of code that produces a value is called an expression.
- Every value that is written literally is an expression.
- Expressions can contain other expressions in a way similiar to how subsentences in human languages are nested.
- A program is a list of statements
- The simplist kind of statement is an expression with a semicolon after it.
- A statement stands on its own, so it amounts to something only if it affects the world.

2. Bindings

- Bindings are variables
- let caught = 5 \* 5;
  - That’s a second kind of statement. The special word (keyword) let indicates that this sentence is going to define a binding. It is followed by the name of the binding and, if we want to immediately give it a value, by an = operator and an expression.
- After a binding has been defined, its name can be used as an expression. The value of such expression is the value that the binding currently holds.
- Bindings do not contain values; they grasp them. Two bindings can refer to the same value.
- If you ask for the value of an empty binding, you'll get the value of undefined.
- const stands for constant, and it defines a constant binding, which points at the same value for as long as it lives.

3. Binding Names

- Bindings cannot start with a digit
- Bindings can include dollar signs($) or underscores(\_) but no other punctuation or special characters.
- Keywords may not be used as binding names(let, const). There is also a list of reserved words that cannot be used.

4. The Environment

- The collection of bindings and their values that exist at a given time is called the environment.

5. Functions

- A function is a piece of program wrapped in a value. Such values can be applied in order to run the wrapped program.
  - 'prompt' holds a function that shows a dialog box asking for user unput.
    - prompt('Enter Password');
- Executing a function is called invoking, calling, or applying it.
- You can call a function by putting parantheses after an expression that produces a function value.
  - The value between the parantheses are given to the program inside the function.
- Values given to functions are called arguments.

6. The Console.Log Function

- Most JavaScript systems provide a console.log function that writes out its arguments to some text output device. In browswers, the output lands in the console.
- console.log isn’t a simple binding. It is actually an expression that retrieves the log property from the value held by the console binding.

7. Return Values

- When a function produces a value, it is said to return that value.
- Function calls can be used within larger expressions.

8. Control Flow

- When programs contain more than one statement, that statements are executed as if they are a story, from top to bottom.

9. Conditional Execution

- Conditional execution is created with the 'if' keyword.
- We may want to create a branching road, where the program takes the proper branch based on the situation at hand.
- The 'if' keyword executes or skips a statement depending on the value of a Boolean expression. The deciding expression is written after the keyword, between parantheses, followed by the statement to execute.
- The braces {} can be used to group any number of statements into a single statement, called a block.
- You can use the 'else' keyword together with if, to create two separate, alternative execution paths.

let theNumber = Number(prompt("Pick a number"));
if (!Number.isNaN(theNumber)) {
console.log("Your number is the square root of " +
theNumber \* theNumber);
} else {
console.log("Hey. Why didn't you give me a number?");
}

- If you have more than two paths to choose from, you can 'chain' multiple if/else pairs together.

10. While and Do Loops

- Looping control flows allow us to go back to some point in the program where we were before and repeat it with our current program state.
- A statement starting with the keyword 'while' creates a loop. The word while is followed by an expression in parantheses and then a statement, much like if. The loop keeps entering that statement as long as the expression produces a value that gives true when converted to a boolean.

let number = 0;
while (number <= 12) {
console.log(number);
number = number + 2;
}

- First a “counter” binding is created to track the progress of the loop. Then comes a while loop, usually with a test expression that checks whether the counter has reached its end value. At the end of the loop body, the counter is updated to track progress.
- The 'do' loop is a control structure similar to a while loop. It differs only on one point:
  - a do loop always executes its body at least once, and it starts testing whether it should stop only after that first execution.

let yourName;
do {
yourName = prompt("Who are you?");
} while (!yourName);
console.log(yourName);

11. Indenting Code

- The role of indentation inside blocks is to make the structure of the code stand out. With proper indentation, the visual shape of a program corresponds to the shape of the blocks inside it.

12. For Loops

- JavaScript and similar languages provide a slightly shorter and more comprehensive form, the for loop.
  for (let number = 0; number <= 12; number = number + 2) {
  console.log(number);
  }

- This program is exactly equivalent to the earlier even-number-printing example. The only change is that all the statements that are related to the “state” of the loop are grouped together after for.
- The parantheses after a for keyword must contain two semicolons.
  - The part before the first semicolon initializes the loop, usually by defining a binding.
  - The second part is the expression that checks whether the loop must continue.
  - The final part updates the state of the loop after every iteration.
  - In most cases this is shorter and clearer than a while construct.

13. Breaking Out of a Loop

- Having the looping condition produce false is not the only way a loop can finish.
- There is a special statement called break that has the effect of immediately jumping out of the enclosing loop.
- Using the remainder (%) operator is an easy way to test whether a number is divisible by another number. If it is, the remainder of their division is zero.
- If you were to remove that break statement or you accidentally write an end condition that always produces true, your program would get stuck in an infinite loop.

14. Updating Bindings Succinctly

- A program often needs to “update” a binding to hold a value based on that binding’s previous value. JavaScript provides a shortcut for this.
  - counter = counter + 1;
  - counter += 1;

for (let number = 0; number <= 12; number += 2) {
console.log(number);
}

- For counter += 1 and counter -= 1, there are even shorter equivalents: counter++ and counter--.

15. Comments

- A comment is a piece of text that is part of a program but is completely ignored by the computer.
- JavaScript has two ways of writing comments.
  - Single line comment: // (followed by text)
  - Multi-line comment: /\* \*/

Eloquent JavaScript, Chapter 3: Functions

- Functions are the bread and butter of JavaScript programming.
  - Structure larger programs, reduce repetition, to associate names with subprograms, isolate subprograms from each other.

1. Defining a Function

- A function is created with an expression that srtarts with the keyword 'function'.
- Functions have a set of parameters, and a body(contains the statements that are to be executed when the function is called).
- A function can have multiple parameters or no parameters at all.
- A return statement determines the value the function returns.
  - A return keyword without an expression after it will cause the function to return undefined.
- Parameters to a function behave like regular bindings, but their initial values are given by the caller of the function, not the code in the function itself.

2. Bindings and Scope

- Each binding has a scope, which is the part of the program in which the binding is visible.
  - Bindings defined outside of any function or block, the scope is the whole program - you can refer to such bindings wherever you want.
    - These are called global.
- Bindings created for function parameters or declared inside a function can be referenced only in that function, so they are know as local bindings.

///////////////////////////////////////////////////////////////////////////////
4/4/23

Udemy JavaScript Course: Section 9: Data Structures, Modern Operators, and Strings

1. Destructuring

- Unpacking values from an array or an object into separate variables.
- Destructing allows you to break a complex data structure down into a smaller data structure.
- Desturcting to retrieve elements from an array and store them into variables in an easy way.

const arr = [2, 3, 4];
const [x, y, z] = arr;
console.log(x, y, z);

const restaurant = {
name: 'Classico Italiano',
location: 'Via Angelo Tavanti 23, Firenze, Italy',
categories: ['Italian', 'Pizzeria', 'Vegetarian', 'Organic'],
starterMenu: ['Focaccia', 'Bruschetta', 'Garlic Bread', 'Caprese Salad'],
mainMenu: ['Pizza', 'Pasta', 'Risotto'],

order: function (starterIndex, mainIndex) {
return [this.starterMenu[starterIndex], this.mainMenu[mainIndex]];
},
};

let [main, , secondary] = restaurant.categories;
console.log(main, secondary); // Italian Vegetarian

// Switching variables
[main, secondary] = [secondary, main];
console.log(main, secondary); // Vegetarian Italian

restaurant.order(2, 0);
console.log(restaurant.order(2, 0)); // (2) ['Garlic Bread', 'Pizza']

// Receive 2 return values from a function
const [starter, mainCourse] = restaurant.order(2, 0);
console.log(starter, mainCourse); // Garlic Bread Pizza

// Nested Destructuring
const nested = [2, 4, [5, 6]];
// const [i, , j] = nested;
// console.log(i, j); // 2, [5, 6]

const [i, , [j, k]] = nested;
console.log(i, j, k); // 2 5 6

// Default Values
const [p = 1, q = 1, r = 1] = [8, 9];
console.log(p, q, r); // 8 9 1

2. Destructuring Objects

- Curly braces are used to destructure objects.
  const { name, openingHours, categories } = restaurant;
  - Creates 3 new variables based on the object.
- Helps to reduce code

const restaurant = {
name: 'Classico Italiano',
location: 'Via Angelo Tavanti 23, Firenze, Italy',
categories: ['Italian', 'Pizzeria', 'Vegetarian', 'Organic'],
starterMenu: ['Focaccia', 'Bruschetta', 'Garlic Bread', 'Caprese Salad'],
mainMenu: ['Pizza', 'Pasta', 'Risotto'],
openingHours: {
thu: {
open: 12,
close: 22,
},
fri: {
open: 11,
close: 23,
},
sat: {
open: 0,
close: 24,
},
},

order: function (starterIndex, mainIndex) {
return [this.starterMenu[starterIndex], this.mainMenu[mainIndex]];
},

orderDelivery: function ({
starterIndex = 1,
mainIndex = 0,
time = '20:00',
address,
}) {
console.log(
`Order received! ${this.starterMenu[starterIndex]} and ${this.mainMenu[mainIndex]} will be delivered to ${address} at ${time}.`
);
},
};

restaurant.orderDelivery({
time: '22:30',
address: 'Via de Sole, 21',
mainIndex: 2,
starterIndex: 2,
});

restaurant.orderDelivery({
address: 'Via de Sole, 21',
starterIndex: 1,
});

const { name, openingHours, categories } = restaurant;
console.log(name, openingHours, categories); // Classico Italiano {thu: {…}, fri: {…}, sat: {…}} (4) ['Italian', 'Pizzeria', 'Vegetarian', 'Organic']

const {
name: restaurantName,
openingHours: hours,
categories: tags,
} = restaurant;
console.log(restaurantName, hours, tags); // Classico Italiano {thu: {…}, fri: {…}, sat: {…}} (4) ['Italian', 'Pizzeria', 'Vegetarian', 'Organic']

// Default Values
const { menu = [], starterMenu: starters = [] } = restaurant;
console.log(menu, starters); // [] (4) ['Focaccia', 'Bruschetta', 'Garlic Bread', 'Caprese Salad']

// Mutating Variables
let a = 111;
let b = 999;
const obj = { a: 23, b: 7, c: 14 };
({ a, b } = obj); // Have to wrap in parantheses to avoid unexpected token error
console.log(a, b); // 23, 7

// Nested Objects
const {
fri: { open, close },
} = openingHours;
console.log(open, close); // 11 23
