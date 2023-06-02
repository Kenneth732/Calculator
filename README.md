# Business Logic
> The business logic section contains functions for performing mathematical operations. Each function takes two numbers as input and returns the result of the corresponding operation. The available operations are addition, subtraction, multiplication, and division.


```
function add(num1, num2) {
    return num1 + num2;
}

function subtract(num1, num2) {
    return num1 - num2;
}

function multiply(num1, num2) {
    return num1 * num2;
}

function divide(num1, num2) {
    return num1 / num2;
}


```

# User Interface Logic

> The user interface logic handles the interaction with the calculator form and displays the result.

```
function handleCalculation(event) {
    event.preventDefault();

    // Retrieve the input values from the form
    const number1 = parseInt(document.querySelector("input#input1").value);
    const number2 = parseInt(document.querySelector("input#input2").value);
    const operator = document.querySelector("input[name='operator']:checked").value;

    let result;

    // Perform the calculation based on the selected operator
    if (operator === "add") {
        result = add(number1, number2);
    } else if (operator === "subtract") {
        result = subtract(number1, number2);
    } else if (operator === "multiply") {
        result = multiply(number1, number2)
    } else if (operator === "divide") {
        result = divide(number1, number2);
    }

    // Display the result
    document.getElementById("output").innerText = result;
}

// Add event listener to the form submission
window.addEventListener("load", function () {
    const form = document.getElementById("calculator");
    form.addEventListener("submit", handleCalculation);
});

```

> When the form is submitted, the handleCalculation function is called. It prevents the default form submission behavior, retrieves the input values from the form, determines the selected operator, performs the corresponding calculation using the business logic functions, and finally displays the result in the output element.

> The window.addEventListener("load", ...) ensures that the event listener for the form submission is added after the window has finished loading, so the form and its elements are accessible.