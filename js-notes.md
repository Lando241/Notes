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
