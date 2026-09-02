[◀ Back](.././)

---

# 7. Understand Modules & Packages
* **What is Importing Modules?**<br>
  **Importing modules** is the process of loading external Python files or libraries into your current script to gain access to their pre-written functions, classes, and variables.

  <details>
  <summary>Click for more</summary>
  
  1. **Standard Library:** Python comes bundled with built-in modules like `math`, `random`, `datetime`, and `os`.
  2. **Import Variations:** You can import an entire module (`import math`), select specific items (`from math import sqrt`), or assign a custom shortcut alias (`import numpy as np`).
  3. **Namespace Safety:** Importing a module using a plain `import` statement keeps functions isolated behind the module name, preventing naming conflicts with your own variables.
  
  **Example Code:**
  ```python
  # Scenario A: Importing an entire module
  import math
  print(math.floor(4.7))  # Outputs: 4

  # Scenario B: Importing a specific tool with an alias
  from random import randint as random_number
  print(random_number(1, 10))  # Outputs a random integer between 1 and 10
  ```
  
  </details>

* **What is Creating Reusable Modules?**<br>
  **Creating reusable modules** is the practice of splitting your own code across separate `.py` files so that individual logic blocks can be imported and shared across multiple projects.

  <details>
  <summary>Click for more</summary>
  
  1. **File Extension:** Any standard Python file (`.py`) containing valid syntax functions or data objects can automatically act as an importable module.
  2. **The Main Gatekeeper:** Using the `if __name__ == "__main__":` idiom allows you to include script-testing code that runs *only* when the file is executed directly, not when imported.
  3. **Module Search Path:** Python searches for your custom files first inside the active directory where your script is being executed.
  
  **Example Code:**
  ```python
  # ---- File 1: calculator.py (The Custom Module) ----
  def multiply_nums(a, b):
      return a * b

  # This block will NOT execute when imported by other files
  if __name__ == "__main__":
      print("Testing module directly...")
      print(multiply_nums(2, 3))

  # ---- File 2: main.py (The Main Program) ----
  import calculator

  result = calculator.multiply_nums(5, 4)
  print(f"Result from custom module: {result}")  # Outputs: 20
  ```
  
  </details>

* **What is Package Organization?**<br>
  **Package organization** is a systematic structural method where multiple related Python modules are cataloged together within an organized folder directory tree.

  <details>
  <summary>Click for more</summary>
  
  1. **Directory Concept:** A package is essentially a standard system folder that holds sub-folders and module files.
  2. **The Initializer File:** Historically, folders required a blank file named `__init__.py` to be explicitly recognized by Python as a package (optional but recommended in modern Python).
  3. **Dot Notation:** Nested sub-modules within packages are retrieved by chaining dots together during import operations (e.g., `import package.subpackage.module`).
  
  **Visual Directory Structure:**
  ```text
  my_project/
  │
  ├── main.py                  # Main execution script
  └── ecommerce/               # This folder acts as our Package
      ├── __init__.py          # Initializes the package
      ├── payment.py           # Module inside ecommerce package
      └── shipping.py          # Module inside ecommerce package
  ```
  
  **Example Code (main.py):**
  ```python
  # Importing a module directly out of our project package folder
  from ecommerce import payment, shipping

  payment.process_invoice(150)
  shipping.calculate_delivery()
  ```
  
  </details>

* **What are Virtual Environments?**<br>
  A **virtual environment** is a completely isolated local sandbox folder workspace that contains its own specific copy of Python and separate installed project dependency libraries.

  <details>
  <summary>Click for more</summary>
  
  1. **The Core Problem:** Different projects often require conflicting versions of third-party packages (e.g., Project A needs Library v1.0, Project B needs Library v2.0).
  2. **Isolation Benefit:** Virtual environments prevent system-wide software clutter and breakages by containing packages entirely inside the active project folder.
  3. **The Standard Tool:** Created natively on your computer terminal via the built-in system module utility `venv`.
  
  **Terminal Command Samples:**
  ```bash
  # 1. Create a virtual environment named 'my_env' inside your directory
  python -m venv my_env

  # 2. Activate the environment (Windows)
  my_env\Scripts\activate

  # 3. Activate the environment (Mac/Linux macOS)
  source my_env/bin/activate

  # 4. Deactivate the environment when done
  deactivate
  ```
  
  </details>

* **What is Dependency Management?**<br>
  **Dependency management** is the process of tracking, installing, updating, and documenting external third-party tools and packages that your software requires to run.

  <details>
  <summary>Click for more</summary>
  
  1. **The Package Manager:** Python uses `pip` as its standard system tool to locate, download, and install third-party libraries from the official repository ([PyPI](https://pypi.org)).
  2. **The Blueprint File:** Dependencies are tracked globally for a project inside a standardized text file named `requirements.txt`.
  3. **Replicability:** Anyone can perfectly clone, set up, and launch your code by feeding your `requirements.txt` manifest into their local environment manager.
  
  **Terminal & File Samples:**
  ```bash
  # Installing an open-source library via terminal
  pip install requests

  # Exporting your active project dependency list into a file
  pip freeze > requirements.txt
  ```
  
  **Contents of requirements.txt:**
  ```text
  requests==2.31.0
  numpy==1.26.2
  pandas==2.1.3
  ```
  
  ```bash
  # How another developer installs all matching dependencies from your file
  pip install -r requirements.txt
  ```
  
  </details>


---

[◀ Back](.././)