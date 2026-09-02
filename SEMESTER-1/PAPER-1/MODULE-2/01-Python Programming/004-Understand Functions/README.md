# 4. Understand Functions
* **What is Function Creation?**<br>
  **Function creation** is the process of defining a reusable block of code that performs a specific task and only runs when explicitly called.

  <details>
  <summary>Click for more</summary>
  
  1. **Syntax:** Defined using the `def` keyword, followed by the function name and parentheses (e.g., `def greet():`).
  2. **Structure:** The code block inside the function must be properly indented to show it belongs to that function.
  3. **Execution:** Creating a function only stores the logic; it will not execute until you call it by its name with parentheses (e.g., `greet()`).
  
  </details>

* **What are Parameters?**<br>
  **Parameters** are variables listed inside the input parentheses of a function definition that act as placeholders for incoming data.

  <details>
  <summary>Click for more</summary>
  
  1. **Arguments vs Parameters:** Parameters are the variables inside the function definition, while arguments are the actual values passed during the call.
  2. **Positional Arguments:** By default, arguments must be passed in the exact same sequential order as their corresponding parameters.
  3. **Default Parameters:** You can assign a fallback value directly in the definition (e.g., `def greet(name="Guest"):`) to use if an argument is missing.
  
  </details>

* **What are Return Values?**<br>
  A **return value** is the final data result that a function sends back to the main program line where the function call originated.

  <details>
  <summary>Click for more</summary>
  
  1. **The Keyword:** Handled using the `return` statement, which instantly terminates function execution.
  2. **Output Storage:** Returning a value allows you to capture and save the function's output directly inside a variable.
  3. **Default Behavior:** If a function does not contain an explicit `return` statement, it automatically outputs `None` by default.
  
  </details>

* **What is Scope?**<br>
  **Scope** refers to the specific region of a program code where a particular variable is recognized, accessible, and can be modified.

  <details>
  <summary>Click for more</summary>
  
  1. **Local Scope:** Variables created directly inside a function can only be read or used within that specific function block.
  2. **Global Scope:** Variables created outside of all functions are available globally across the entire script file.
  3. **Lifetime:** Local variables are completely wiped from computer memory as soon as their host function finishes running.
  
  </details>

* **What is Reusable Logic?**<br>
  **Reusable logic** is the software practice of writing code once inside a function so it can be safely executed multiple times across a program without duplication.

  <details>
  <summary>Click for more</summary>
  
  1. **DRY Principle:** Keeps code clean according to the "Don't Repeat Yourself" programming rule to reduce structural copy-pasting.
  2. **Modularity:** Breaks a large, complex application down into isolated, self-contained mini-tasks that are easier to debug.
  3. **Maintenance:** Updating a formula inside a single shared function automatically updates the behavior across your entire application.
  
  </details>
