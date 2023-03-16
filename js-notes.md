Notes on Javascript:

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

- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence#table
