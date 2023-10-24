# MODULE 3–JAVASCRIPT OBJECTS, ARRAYS, OPERATORS, AND CONDITIONS

In this comprehensive module, you will master the skills of working with JavaScript's core elements such as objects, arrays, operators, and conditional statements. Understanding these concepts will enable you to manipulate data, perform operations, and control the flow of your programs.

## Learning Outcomes
Upon successful completion of this module, you will be proficient in the following areas:

1. Describe JavaScript objects
2. Define JavaScript arrays
3. Identify JavaScript arithmetic operators
4. Understand assignment operators in JavaScript
5. Explain JavaScript conditional statements and operators
6. Code simple JavaScript programs using different arrays and operations

---

## Lesson 1: JavaScript Objects and Arrays

### What is an Object?

In Object-Oriented Programming (OOP), an object is the cornerstone. It represents an entity that can store data and have actions that can be performed on it. Each object is an instance of a class, which can have attributes (variables) and methods (functions) associated with it.

### What are JavaScript Objects?

In JavaScript, objects are key-value pairs where the key is the property name, and the value is the property's value. These properties can be either variables or functions. When a function is a property of an object, it's called a **method**. 

#### Accessing Object Properties

You can access an object's properties using dot-notation or bracket-notation. Here's a simple example that uses dot-notation:

```html
<html>
 <head>
 <script>
 let Computer = new Object();
 Computer.type = "PC";
 Computer.os = "Windows";
 Computer.memory = "16GB";
 console.log(Computer.type);
 console.log(Computer.os);
 </script>
 </head>
 <body></body>
</html>
```

#### Example Using Bracket Notation
In some cases, especially when property names have spaces or special characters, bracket notation comes in handy.

```html
<html>
 <head>
 <script>
 let Computer = new Object();
 Computer.type = "PC";
 Computer.os = "Windows";
 Computer["memory"] = "16GB";
 console.log(Computer["type"]);
 console.log(Computer["os"]);
 </script>
 </head>
 <body></body>
</html>
```

#### Object Methods

You can also declare methods within an object. Methods are essentially functions that belong to an object.

```html
<html>
 <head>
 <script>
 let Computer = {
  type: "PC",
  os: "Windows",
  memory: "16GB",
  specs: function () {
    return "This a " + this.os + " " + this.type + " with " + this.memory + " of memory.";
  },
 };
 console.log(Computer.specs());
 </script>
 </head>
 <body></body>
</html>
```

### What is an Array?

Arrays are a collection of elements, usually of the same data type, and are stored in contiguous memory locations. They can hold multiple values at the same time.

#### Creating Arrays

```html
<html>
 <head>
 <script>
 var students = ["John", "Ann", "Jane", "Moe"];
 </script>
 </head>
 <body></body>
</html>
```

#### Accessing Array Elements
Array elements can be accessed using indices. Remember that arrays in JavaScript are zero-indexed, meaning the first element is accessed with index 0.

```html
<html>
 <head>
 <script>
 var students = ["John", "Ann", "Jane", "Moe"];
 console.log(students[0]); // Outputs "John"
 </script>
 </head>
 <body></body>
</html>
```

#### Changing Array Elements
Array elements can be replaced using the index number.

```html
<html>
 <head>
 <script>
 var students = ["John", "Ann", "Jane", "Moe"];
 students[0] = "Nav";
 console.log(students[0]); // Outputs "Nav"
 </script>
 </head>
 <body></body>
</html>
```

### Array Methods
JavaScript provides several built-in methods to manipulate arrays. For instance, `.sort()` sorts an array and `.push()` adds a new element to an array.

```html
<html>
 <head>
 <script>
 var students = ["John", "Ann", "Jane", "Moe"];
 console.log(students.length);  // Outputs 4
 students.sort(); // Sorts the array
 console.log(students); // Outputs sorted array
 </script>
 </head>
 <body></body>
</html>
```

### In-Class Exercise 1: Working with Arrays

1. **brandsCount Function**: Create a function that prints the length of the array to the console.
2. **More Than Ten**: Write a function that returns true if there are more than ten elements in the array, otherwise returns false.

#### Solution Instructions for Exercise 1

```html
<html>
 <head>
 <script>
  var brands = ["Apple", "Samsung", "Mercedes", "Burger King"];
  
  // Function to print the length of the array
  function brandsCount() {
    console

.log(brands.length);
  }
  
  // Function to check if array length is more than 10
  function moreThanTen() {
    return brands.length > 10;
  }
  
  // Test the functions
  brandsCount();
  console.log(moreThanTen());
 </script>
 </head>
 <body></body>
</html>
```

That concludes Lesson 1 of Module 3. We will continue exploring JavaScript operators and conditional statements in Lesson 2.

## Lesson 2: JavaScript Operators and Conditional Statements

### Arithmetic Operators

JavaScript provides a set of arithmetic operators for performing basic calculations. These include:

- Addition (`+`)
- Subtraction (`-`)
- Multiplication (`*`)
- Division (`/`)
- Modulus (remainder after division) (`%`)

| Operator | Description    | Example     | Result |
|----------|----------------|-------------|--------|
| `+`      | Addition       | `10 + 5`    | `15`   |
| `-`      | Subtraction    | `10 - 5`    | `5`    |
| `*`      | Multiplication | `10 * 5`    | `50`   |
| `/`      | Division       | `10 / 5`    | `2`    |
| `%`      | Modulus        | `10 % 3`    | `1`    |

#### Example: Arithmetic Operators

```html
<html>
  <head>
    <script>
      let a = 10, b = 5;
      console.log(a + b); // Output: 15
      console.log(a - b); // Output: 5
      console.log(a * b); // Output: 50
      console.log(a / b); // Output: 2
      console.log(a % b); // Output: 0
    </script>
  </head>
  <body></body>
</html>
```

### Assignment Operators

Assignment operators are used to assign a value to a variable.

- Basic assignment (`=`)
- Add and assign (`+=`)
- Subtract and assign (`-=`)
- Multiply and assign (`*=`)
- Divide and assign (`/=`)


| Operator | Description         | Example       | Result |
|----------|---------------------|---------------|--------|
| `=`      | Assign              | `x = 10`      | `10`   |
| `+=`     | Add and Assign      | `x += 5`      | `15`   |
| `-=`     | Subtract and Assign | `x -= 5`      | `5`    |
| `*=`     | Multiply and Assign | `x *= 5`      | `50`   |
| `/=`     | Divide and Assign   | `x /= 5`      | `2`    |


#### Example: Assignment Operators

```html
<html>
  <head>
    <script>
      let x = 10;
      x += 5; // Equivalent to x = x + 5;
      console.log(x); // Output: 15
    </script>
  </head>
  <body></body>
</html>
```

### Conditional Statements

Conditional statements are used to make decisions in your code. The primary forms of conditional statements in JavaScript are `if`, `else if`, and `else`.

| Operator | Description                        | Example                  | Result  |
|----------|------------------------------------|--------------------------|---------|
| `==`     | Equal to                           | `5 == "5"`               | `true`  |
| `===`    | Strictly equal to (type + value)   | `5 === "5"`              | `false` |
| `!=`     | Not equal to                       | `5 != "6"`               | `true`  |
| `!==`    | Strictly not equal to              | `5 !== "5"`              | `true`  |
| `>`      | Greater than                       | `5 > 3`                  | `true`  |
| `<`      | Less than                          | `3 < 5`                  | `true`  |
| `>=`     | Greater than or equal to           | `5 >= 5`                 | `true`  |
| `<=`     | Less than or equal to              | `5 <= 6`                 | `true`  |

#### Example: Conditional Statements

```html
<html>
  <head>
    <script>
      let score = 75;
      if (score >= 90) {
        console.log("A");
      } else if (score >= 80) {
        console.log("B");
      } else if (score >= 70) {
        console.log("C");
      } else {
        console.log("F");
      }
    </script>
  </head>
  <body></body>
</html>
```

### In-Class Exercise 2: Working with Operators and Conditions

1. **Calculation Function**: Create a function that accepts two numbers and an operator (either `+`, `-`, `*`, or `/`). The function should perform the operation on the numbers and return the result.
2. **Grade Calculation**: Write a function that accepts a student's score and returns the grade (A, B, C, D, F).

#### Solution Instructions for Exercise 2

```html
<html>
  <head>
    <script>
      // Function to perform the arithmetic operations
      function calculate(a, b, operator) {
        if (operator === "+") return a + b;
        if (operator === "-") return a - b;
        if (operator === "*") return a * b;
        if (operator === "/") return a / b;
        return "Invalid operator";
      }

      // Function to determine grade
      function gradeCalculation(score) {
        if (score >= 90) return "A";
        if (score >= 80) return "B";
        if (score >= 70) return "C";
        if (score >= 60) return "D";
        return "F";
      }

      // Test the functions
      console.log(calculate(10, 5, "+")); // Output: 15
      console.log(gradeCalculation(85)); // Output: B
    </script>
  </head>
  <body></body>
</html>
```

That concludes Lesson 2 and Module 3. You are now equipped to use objects, arrays, operators, and conditional statements in JavaScript to create more dynamic and interactive applications.

Absolutely, let's break it down into more detailed steps and explanations.

---

### Exercise: Temperature Converter (Detailed Version)

#### What You Will Learn
- How to capture user input from HTML form elements.
- How to use radio buttons to specify options.
- How to apply basic math formulas in JavaScript.
- How to update HTML content from JavaScript.

---

#### Step 1: Create HTML Layout

##### What You'll Do:
Create the HTML layout for the temperature converter.

##### Code:
Create a new HTML file and add this code:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Temperature Converter</title>
</head>
<body>

  <h1>Temperature Converter</h1>

  <form id="tempForm">
    <label for="temperature">Temperature:</label>
    <input type="number" id="temperature" name="temperature">
    
    <label>
      <input type="radio" name="unit" value="F"> Fahrenheit
    </label>

    <label>
      <input type="radio" name="unit" value="C"> Celsius
    </label>

    <input type="button" value="Convert" onclick="convertTemperature()">
  </form>

  <p id="result"></p>

</body>
</html>
```

##### Tips:
- Use the `<input type="number">` to restrict input to numerical values.
- The `onclick` attribute runs JavaScript code when the button is clicked.

---

#### Step 2: Write JavaScript Function

##### What You'll Do:
Write the JavaScript function to perform the temperature conversion.

##### Code:

Inside the `<head>` tag, add the following code:

```javascript
<script>
  function convertTemperature() {
    // Step 2.1: Get the temperature from the input field
    var temp = document.getElementById("temperature").value;

    // Step 2.2: Convert the temperature string to a number
    var tempNumber = Number(temp);

    // Step 2.3: Get the selected unit (F or C)
    var unitElement = document.querySelector('input[name="unit"]:checked');
    var unit = unitElement.value;

    // Step 2.4: Perform the conversion
    var convertedTemp;
    if (unit === "F") {
      convertedTemp = (tempNumber - 32) * (5 / 9);
    } else {
      convertedTemp = (tempNumber * 9 / 5) + 32;
    }

    // Step 2.5: Display the result
    document.getElementById("result").innerText = "Converted Temperature: " + convertedTemp.toFixed(2);
  }
</script>
```

##### Tips & Explanation:

1. **`document.getElementById("temperature").value`:** This code retrieves the value entered in the input field with the id "temperature".
   
2. **`Number(temp)`:** This converts the temperature string to a number. It's similar to `parseFloat()`, but simpler. It converts a string to a number.

3. **`document.querySelector()`:** This method retrieves the first element that matches the specified selectors. In our case, it gets the radio button that is checked (`input[name="unit"]:checked`).

4. **`unitElement.value`:** This retrieves the value ("F" or "C") of the selected radio button.

5. **`convertedTemp.toFixed(2)`:** This method rounds the number to 2 decimal places.

---

#### Step 3: Test Your Application

Save your HTML file and open it with a web browser. Try entering different temperatures and selecting different units.

---

And that’s it! You have now built a temperature converter. You've practiced HTML forms, JavaScript variables, conditionals, and functions, all in a practical, real-world example.

Certainly! Let's explore how to create a Password Strength Checker.

---

### Exercise: Password Strength Checker

#### What You Will Learn

- How to work with HTML input fields, particularly the password field.
- How to use JavaScript to check the strength of a password.
- How to dynamically update the HTML to display the strength of the password.

---

#### Step 1: Create HTML Layout

##### What You'll Do
Create the HTML layout for the password strength checker.

##### Code
Create a new HTML file and add the following code:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Password Strength Checker</title>
</head>
<body>

  <h1>Password Strength Checker</h1>

  <form id="passwordForm">
    <label for="password">Enter your password:</label>
    <input type="password" id="password" name="password" onkeyup="checkPasswordStrength()">
    <p id="strength"></p>
  </form>

</body>
</html>
```

##### Tips
- The `<input type="password">` field hides the characters entered.

---

#### Step 2: Write JavaScript Function

##### What You'll Do
Write the JavaScript function to check the password strength.

##### Code
Inside the `<head>` tag, add the following JavaScript code:

```javascript
<script>
  function checkPasswordStrength() {
    // Step 2.1: Get the password from the input field
    var password = document.getElementById("password").value;

    // Step 2.2: Initialize a variable to store password strength
    var strength = "Weak";

    // Step 2.3: Check password strength conditions
    if (password.length >= 8 && /[a-z]/.test(password) && /[A-Z]/.test(password) && /[0-9]/.test(password)) {
      strength = "Strong";
    } else if (password.length >= 8) {
      strength = "Moderate";
    }

    // Step 2.4: Display the strength
    document.getElementById("strength").innerText = "Password Strength: " + strength;
  }
</script>
```

##### Tips & Explanation

1. **Getting Password**: `document.getElementById("password").value` fetches the password input from the user.

2. **Checking Conditions**: We use conditions to check the strength:
    - Length of at least 8 characters.
    - Contains lowercase and uppercase letters.
    - Contains numbers.

3. **Display Strength**: Finally, we display the password strength dynamically as the user types.

And that's your Password Strength Checker! This will provide real-time feedback to the user about the strength of their password.


### Exercise: Quiz App

#### What You Will Learn

- How to handle multiple HTML input types like radio buttons.
- How to use arrays and loops in JavaScript.
- How to display the final score dynamically.

---

#### Step 1: Create HTML Layout

##### What You'll Do
Create the HTML layout for the quiz app.

##### Code
Create a new HTML file and add the following code:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Simple Quiz App</title>
</head>
<body>

  <h1>Simple Quiz App</h1>

  <form id="quizForm">
    <div class="question">
      <p>1. What is the capital of France?</p>
      <input type="radio" name="q1" value="Berlin"> Berlin
      <input type="radio" name="q1" value="Paris"> Paris
    </div>

    <div class="question">
      <p>2. Which is the largest planet?</p>
      <input type="radio" name="q2" value="Earth"> Earth
      <input type="radio" name="q2" value="Jupiter"> Jupiter
    </div>

    <button type="button" onclick="calculateScore()">Submit</button>
  </form>

  <p id="score"></p>

</body>
</html>
```

##### Tips
- We use radio buttons (`<input type="radio">`) for answer choices. All radio buttons with the same `name` attribute will belong to the same group.

---

#### Step 2: Write JavaScript Function

##### What You'll Do
Write the JavaScript function to calculate and display the score.

##### Code
Inside the `<head>` tag, add the following JavaScript code:

```javascript
<script>
  function calculateScore() {
    // Step 2.1: Initialize score variable
    var score = 0;

    // Step 2.2: Fetch selected answers
    var answer1 = document.querySelector('input[name="q1"]:checked').value;
    var answer2 = document.querySelector('input[name="q2"]:checked').value;

    // Step 2.3: Check answers and calculate score
    if (answer1 === "Paris") score++;
    if (answer2 === "Jupiter") score++;

    // Step 2.4: Display score
    document.getElementById("score").innerText = "Your Score: " + score;
  }
</script>
```

##### Tips & Explanation

1. **Initializing Score**: We start with a `score` of 0.
2. **Fetching Selected Answers**: The `document.querySelector('input[name="q1"]:checked').value` method fetches the value of the selected radio button for each question.
3. **Checking Answers**: We compare the selected answers to the correct ones to calculate the score.
4. **Displaying Score**: Finally, the score is displayed on the web page using `getElementById()`.

---

There you go! With this setup, students will be able to take a simple quiz and get their scores immediately after clicking the "Submit" button.

### Cheat Sheet

Certainly, here's a more complete reference table including the additional elements:

| Line Description               | Syntax or Element                | Purpose                                                                      | Example                                |
|--------------------------------|----------------------------------|------------------------------------------------------------------------------|----------------------------------------|
| Declare Variable               | `var variableName = value;`      | To declare a variable                                                        | `var x = 10;`                          |
| Function Declaration           | `function functionName() { }`    | To declare a function                                                        | `function greet() { }`                 |
| Function Call                  | `functionName();`                | To execute a function                                                        | `greet();`                             |
| Console Log                    | `console.log(value);`            | To print a value to the console                                              | `console.log("Hello");`                |
| If Statement                   | `if (condition) { }`             | To execute code block if condition is true                                   | `if (x > 0) { }`                       |
| Else Statement                 | `else { }`                       | To execute code block if condition is false                                  | `else { }`                             |
| Else If Statement              | `else if (condition) { }`        | To check another condition if previous conditions are false                   | `else if (x == 0) { }`                 |
| Return Statement               | `return value;`                  | To return a value from a function                                            | `return x;`                            |
| Create Array                   | `var arrayName = [ ];`           | To declare an array                                                          | `var numbers = [1, 2, 3];`              |
| For Loop                       | `for(init; condition; iteration)`| To loop through a block of code                                              | `for (i=0; i<5; i++) { }`               |
| Push to Array                  | `arrayName.push(value);`         | To add an element to the end of an array                                     | `numbers.push(4);`                     |
| Parse Float                    | `parseFloat(string);`            | To convert a string to a floating-point number                               | `var num = parseFloat("10.5");`        |
| Arithmetic Operators           | `+ - * / %`                     | For mathematical operations                                                  | `x + y; x - y; x * y; x / y; x % y;`   |
| Comparison Operators           | `== === != !== > < >= <=`        | For comparing values                                                         | `x == y; x != y; x > y; x < y;`        |
| Logical Operators              | `&& \|\| !`                     | For combining conditional statements                                         | `x && y; x \|\| y; !x;`                |
| Query Selector                 | `document.querySelector(css);`   | To select the first element that matches the specified CSS                    | `var el = document.querySelector(".cls");`|
| Add Event Listener             | `.addEventListener(event, func)` | To attach an event to an element                                             | `el.addEventListener("click", func);`  |
| Get Element by ID              | `document.getElementById(id);`  | To get an element by its ID attribute                                        | `var el = document.getElementById("id");`|
| InnerHTML                      | `.innerHTML = string;`           | To get or set the HTML content of an element                                 | `el.innerHTML = "Hello";`              |
| Alert                          | `alert(string);`                 | To display an alert dialog box                                               | `alert("Hello!");`                     |

This table should cover all the JavaScript syntax and elements used in the lesson activities.

Certainly! Below are 20 interview questions covering variables, data types, functions, operators, conditionals, loops, arrays, and DOM manipulation in JavaScript. I've also included answer guides for each question.

### Interview Questions and Answer Guides

#### Variables, Data Types, and Functions

1. **What are the different ways to declare a variable in JavaScript?**
   - `var`, `let`, `const`
  
2. **What are the basic data types in JavaScript?**
   - Number, String, Boolean, Undefined, Null, Symbol, BigInt
  
3. **What is the difference between `==` and `===`?**
   - `==` is equality with type coercion, `===` is strict equality without type coercion.

4. **Can you explain what hoisting is?**
   - Variable and function declarations are moved to the top of their containing scope during compilation.

#### Operators

5. **What does the `+=` operator do?**
   - It adds the value on the right to the variable on the left and assigns the result to the variable on the left.

6. **What is the difference between `++x` and `x++`?**
   - `++x` increments the value of `x` before the current expression is evaluated, `x++` increments after.

7. **How does the ternary operator work?**
   - `(condition) ? (true block) : (false block)`

8. **What does the `&&` operator do?**
   - Logical AND, returns true if both operands are true.

#### Conditionals

9. **What is the basic structure of an `if` statement?**
   - `if (condition) { block of code }`
   
10. **What is the purpose of the `else if` clause?**
    - To check multiple conditions using the same `if` statement.

11. **How do you use a `switch` statement?**
    - `switch(expression) { case x: code block; break; ... default: code block }`

#### Loops

12. **What is the difference between `for` and `while` loops?**
    - `for` loops usually have a counter, `while` loops just need a condition to continue.

13. **How do you stop a loop?**
    - `break` statement.

#### Arrays

14. **How do you add an element to an array?**
    - `array.push(element)`, `array.unshift(element)`, `array[index] = element`

15. **How do you remove the last element from an array?**
    - `array.pop()`

#### DOM Manipulation

16. **How do you select an element with an ID of `myElement`?**
    - `document.getElementById('myElement')`

17. **How do you change the inner HTML of an element?**
    - `element.innerHTML = 'new content'`

18. **What does `addEventListener` do?**
    - It attaches an event handler to an element.

#### General

19. **How do you write a function that takes an argument?**
    - `function myFunc(argument) { // code }`

20. **What does `return` do in a function?**
    - Exits the function, optionally passing back a value.
