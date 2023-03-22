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
