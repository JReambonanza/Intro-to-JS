### MODULE 4–JAVASCRIPT LOOPS, PROMISES, AND ASYNC

#### Lesson 1: JavaScript Loops

##### What is a Loop?

In computer programming, a loop is a sequence of instructions that is continually repeated until a certain condition is reached. A loop is a section of code that will be repeated indefinitely. Loops are classified into two types: "while loops" and "for loops."

##### Why do I need Loops?

Loops are essential for tasks that need to be repeated multiple times. Assume you wish to input the word "Hi" 99 times on your website. You could either write the word 99 times manually or use a loop to accomplish this task in a more efficient way.

##### What are the Different Sub-types of Loops in JavaScript?

JavaScript offers several types of loops to handle different situations. Here we will explore four sub-types:

1. for loops
2. for/in loop
3. while loop
4. do...while loop

#### Additional Topics

###### Loop Control Statements

In JavaScript, the `break` and `continue` statements are used to control the flow of execution inside loops. The `break` statement stops the loop immediately, and the `continue` statement skips the rest of the loop's body for the current iteration and jumps back to the beginning.

###### Nested Loops

Nested loops are loops within loops. They are particularly useful when working with multi-dimensional arrays or when you need to perform repetitive actions on each element of an array.

###### Performance Considerations

When using loops, especially nested loops, be aware that they can be resource-intensive and potentially slow down performance. Use them wisely and test for efficiency whenever possible.

#### In-Class Exercise 1

1. **Loop to Find the Sum**: Loop through an array of numbers and find the sum.

    **Solution:**
    ```html
    <html>
    <head>
    <script>
        var numbers = [1, 2, 3, 4, 5];
        var sum = 0;
        for(var i = 0; i < numbers.length; i++) {
            sum += numbers[i];
        }
        document.write("The sum is: " + sum);
    </script>
    </head>
    <body></body>
    </html>
    ```

2. **Loop to Concatenate Strings**: Loop through an array of strings and concatenate them.

    **Solution:**
    ```html
    <html>
    <head>
    <script>
        var strings = ["Hello", " ", "World", "!"];
        var result = "";
        for(var i = 0; i < strings.length; i++) {
            result += strings[i];
        }
        document.write("The concatenated string is: " + result);
    </script>
    </head>
    <body></body>
    </html>
    ```

3. **Simple Quiz Game**: Create a loop to simulate a simple quiz game, asking multiple-choice questions.

    **Solution:**
    ```html
    <html>
    <head>
    <script>
        var questions = ["What is 2+2?", "What is the capital of France?"];
        var answers = ["4", "Paris"];
        var userAnswers = [];
        
        for(var i = 0; i < questions.length; i++) {
            userAnswers[i] = prompt(questions[i]);
            if(userAnswers[i].toLowerCase() === answers[i].toLowerCase()) {
                document.write("Question " + (i+1) + " is correct.<br>");
            } else {
                document.write("Question " + (i+1) + " is incorrect.<br>");
            }
        }
    </script>
    </head>
    <body></body>
    </html>
    ```

#### Lesson 2: JavaScript Async

##### What is Async/Await?

Async/Await is a modern way to handle asynchronous operations in JavaScript. It makes it easier to work with asynchronous code by providing a more straightforward, cleaner syntax.

##### Error Handling

When working with async/await, error handling becomes crucial to manage failed promises. You can use `try` and `catch` blocks to handle errors gracefully.

#### Additional Topics

###### Instances where Promises are Necessary

In certain scenarios, async/await might not be sufficient, and you'd need to resort to promises. For example, when you need to perform multiple asynchronous operations and wait for them all to complete, `Promise.all()` can be used.

#### In-Class Exercise 2

1. **Promise Simulation**: Create a Promise that simulates fetching data from an API and use async/await to handle it.

    **Solution:**
    ```html
    <html>
    <head>
    <script>
        function fetchData() {
            return new Promise((resolve, reject) => {
                setTimeout(() => {
                    resolve("Data fetched successfully.");
                }, 2000);
            });
        }
        
        async function getData() {
            try {
                const

 data = await fetchData();
                document.write(data);
            } catch (error) {
                document.write("An error occurred: " + error);
            }
        }
        
        getData();
    </script>
    </head>
    <body></body>
    </html>
    ```

2. **Multiple Fetch Operations**: Use Promise.all() to perform multiple fetch operations.

    **Solution:**
    ```html
    <html>
    <head>
    <script>
        async function multipleFetches() {
            const promise1 = new Promise((resolve) => setTimeout(() => resolve("First data"), 1000));
            const promise2 = new Promise((resolve) => setTimeout(() => resolve("Second data"), 2000));
            
            try {
                const [data1, data2] = await Promise.all([promise1, promise2]);
                document.write(`Received data: ${data1}, ${data2}`);
            } catch (error) {
                document.write("An error occurred: " + error);
            }
        }
        
        multipleFetches();
    </script>
    </head>
    <body></body>
    </html>
    ```

3. **Clock Simulation**: Create a simple clock using `setInterval` and Promises.

    **Solution:**
    ```html
    <html>
    <head>
    <script>
        function clock() {
            setInterval(() => {
                const now = new Date();
                document.write(now.toTimeString().split(" ")[0] + "<br>");
            }, 1000);
        }
        
        clock();
    </script>
    </head>
    <body></body>
    </html>
    ```

#### Cumulative Guided Exercise: Fetch Weather Data

Let's create an application that fetches weather information for a given city and displays it. We'll use the OpenWeatherMap API, which is free and doesn't require an API key for limited usage.

```html
<html>
<head>
<script>
    async function fetchWeather(city) {
        const response = await fetch(`http://api.openweathermap.org/data/2.5/weather?q=${city}&appid=b6907d289e10d714a6e88b30761fae22`);
        const data = await response.json();
        
        if(data.cod === 200) {
            document.write(`Weather in ${data.name}: ${data.weather[0].description}.<br>`);
        } else {
            document.write("Could not fetch weather data.<br>");
        }
    }

    var cities = ["New York", "London", "Paris", "Tokyo"];
    for(let i = 0; i < cities.length; i++) {
        fetchWeather(cities[i]);
    }
</script>
</head>
<body></body>
</html>
```

#### Reference Guide

| Line Description           | Syntax or Element   | Purpose                                                 | Example                  |
|----------------------------|---------------------|---------------------------------------------------------|--------------------------|
| Loop initialization        | `for(var i = 0; ...)| To set the initial loop condition                        | `for(var i = 0; i<5; i++)`|
| Promise declaration        | `new Promise()`    | To create a new Promise                                 | `new Promise((resolve, reject) => {...})`|
| Async function declaration | `async function`   | To declare an async function                             | `async function getData()`|
| Await                      | `await`            | To wait for a Promise to resolve or reject               | `await fetchData()`      |
| Try/Catch                  | `try {...} catch(e)| For error handling in async/await                        | `try { ... } catch(error) { ... }`|

#### Interview Questions

1. Explain the difference between `for` and `while` loops.
2. What is `Promise.all()` and when would you use it?
3. Can `await` be used outside of an `async` function? Why or why not?
4. Explain the concept of `race condition` in JavaScript.

Certainly! Below are the improvements to the last section of Module 4, including answered Interview Questions and enhancements to the Cumulative Guided Exercise to use other HTML tags in the body.

---

#### Interview Questions with Answers

1. **Explain the difference between `for` and `while` loops.**

    - **Answer**: A `for` loop is generally used when the number of iterations is known in advance. It has a more compact syntax, where you can declare the loop variable, condition, and increment in a single line. A `while` loop is usually used when the number of iterations is not known beforehand, and it continues as long as the condition specified evaluates to `true`.

2. **What is `Promise.all()` and when would you use it?**

    - **Answer**: `Promise.all()` is a method that takes an array of promises and returns a new Promise that is fulfilled when all of the promises in the array are fulfilled, or rejected if any of them are rejected. You'd use `Promise.all()` when you have multiple independent asynchronous operations that can run concurrently and you need to wait for all of them to complete.

3. **Can `await` be used outside of an `async` function? Why or why not?**

    - **Answer**: No, `await` cannot be used outside of an `async` function. The `await` keyword is only valid within an `async` function and is used to wait for a Promise to resolve or reject. Using it outside an `async` function will result in a syntax error.

4. **Explain the concept of `race condition` in JavaScript.**

    - **Answer**: A race condition occurs when the program’s behavior is dependent on the relative timing of events, such as the order in which threads are scheduled. In JavaScript, race conditions can occur in asynchronous code when the outcomes depend on the timing of callbacks or the resolution of promises.


#### Step-by-Step Exercise: Fetch Weather Data with HTML Elements

##### Step 1: Set Up HTML Structure

Firstly, let's set up the basic HTML structure, including the `<head>` and `<body>` tags.

```html
<html>
<head>
  <!-- JavaScript will go here -->
</head>
<body>
  <!-- HTML elements will go here -->
</body>
</html>
```

##### Step 2: Add HTML Elements in the Body

Next, add the following HTML elements inside the `<body>` tag:

- An `<input>` element for city name input.
- An `<button>` element to trigger the weather data fetching.
- An `<h2>` element to display the city name.
- A `<p>` element to display the weather description.

```html
<body>
  <input type="text" id="city-input" placeholder="Enter city name" />
  <button onclick="getWeather()">Fetch Weather</button>
  <h2 id="city-name"></h2>
  <p id="weather-description"></p>
</body>
```

##### Step 3: Add JavaScript Code

Now, let's add the JavaScript code inside the `<head>` tag, wrapped by a `<script>` tag.

```html
<script>
  // JavaScript code will go here
</script>
```

##### Step 4: Write the fetchWeather Function

Inside the `<script>` tag, write an `async` function named `fetchWeather`. This function will take a city name as an argument, fetch the weather data, and update the HTML elements.

```html
<script>
  async function fetchWeather(city) {
    const response = await fetch(`http://api.openweathermap.org/data/2.5/weather?q=${city}&appid=your_api_key`);
    const data = await response.json();
    if (data.cod === 200) {
      document.getElementById('city-name').innerText = `Weather in ${data.name}`;
      document.getElementById('weather-description').innerText = `Description: ${data.weather[0].description}`;
    } else {
      document.getElementById('city-name').innerText = `Could not fetch weather data for ${city}.`;
    }
  }
</script>
```

##### Step 5: Add the getWeather Function

Still, within the `<script>` tag, add another function called `getWeather` that will read the city name from the input field and call `fetchWeather`.

```html
<script>
  function getWeather() {
    const city = document.getElementById('city-input').value;
    fetchWeather(city);
  }
</script>
```

##### Final Complete Code

Here's the complete code, combining all the steps:

```html
<html>
<head>
  <script>
    async function fetchWeather(city) {
      const response = await fetch(`http://api.openweathermap.org/data/2.5/weather?q=${city}&appid=your_api_key`);
      const data = await response.json();
      if (data.cod === 200) {
        document.getElementById('city-name').innerText = `Weather in ${data.name}`;
        document.getElementById('weather-description').innerText = `Description: ${data.weather[0].description}`;
      } else {
        document.getElementById('city-name').innerText = `Could not fetch weather data for ${city}.`;
      }
    }
  
    function getWeather() {
      const city = document.getElementById('city-input').value;
      fetchWeather(city);
    }
  </script>
</head>
<body>
  <input type="text" id="city-input" placeholder="Enter city name" />
  <button onclick="getWeather()">Fetch Weather</button>
  <h2 id="city-name"></h2>
  <p id="weather-description"></p>
</body>
</html>
```

Remember to replace `your_api_key` with an actual OpenWeatherMap API key.

This concludes Module 4. Feel free to ask questions and practice with the exercises. Happy Learning!
