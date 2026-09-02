[◀ Back](.././)

---

## 8. Develop Problem Solving Skills
* **What are Number-Based Problems?**<br>
  **Number-based problems** focus on evaluating mathematical logic, properties of integers, sequences, and arithmetic algorithms to solve precise numerical puzzles.

  <details>
  <summary>Click for more</summary>
  
  1. **Core Concept:** Often involves mathematical checks like primality testing, factorization, finding greatest common divisors (GCD), or parsing digits out of an integer.
  2. **Modulo Operator:** The `%` (remainder) operator is critical for tracking patterns, loops, and handling divisibility.
  3. **Efficiency:** Optimizing math loops (e.g., looping up to the square root of a number rather than the full number) drastically saves computational overhead.
  
  **Example Code (Prime Number Checker):**
  ```python
  def is_prime(n):
      if n <= 1:
          return False
      # Optimize loop limit by checking up to the square root of n
      for i in range(2, int(n**0.5) + 1):
          if n % i == 0:
              return False  # Found a divisor, not prime
      return True

  print(is_prime(11))  # Outputs: True
  print(is_prime(4))   # Outputs: False
  ```
  
  </details>

* **What are Collection-Based Problems?**<br>
  **Collection-based problems** involve processing, filtering, and organizing multiple items stored inside lists, sets, tuples, or dictionaries.

  <details>
  <summary>Click for more</summary>
  
  1. **Core Concept:** Solves scenarios requiring tracking frequencies, finding unique combinations, or extracting target pairs.
  2. **Lookups & Storage:** Using sets or dictionaries shifts item checking from a slow search (O(n) time) to an instantaneous lookup (O(1) time).
  3. **Aggregations:** Common exercises require counting duplicates, grouping raw properties, or finding extreme maximum/minimum items under strict criteria.
  
  **Example Code (Two-Sum Tracking using a Set):**
  ```python
  def has_pair_with_sum(nums, target_sum):
      seen_numbers = set()
      for num in nums:
          complement = target_sum - num
          if complement in seen_numbers:
              return True  # Found the matching pair!
          seen_numbers.add(num)
      return False

  print(has_pair_with_sum([4, 1, 2, 7], 9))  # Outputs: True (since 2 + 7 = 9)
  ```
  
  </details>

* **What is String Manipulation?**<br>
  **String manipulation** is the practice of parsing, formatting, cleansing, and validating textual strings to extract structured patterns or verify conditions.

  <details>
  <summary>Click for more</summary>
  
  1. **Immutability:** Strings cannot be changed in place; modification operations always generate an entirely new string behind the scenes.
  2. **Slicing:** Moving backward or forward through text arrays effortlessly using step syntax (e.g., `text[::-1]` to completely reverse a word).
  3. **Built-in Methods:** Harnessing robust native features like `.strip()`, `.split()`, `.join()`, and case methods (`.lower()`, `.upper()`) to sanitize input data.
  
  **Example Code (Clean Palindrome Validator):**
  ```python
  def is_palindrome(text):
      # Clean the text: convert to lowercase and remove spaces
      cleaned = "".join(text.split()).lower()
      # Compare the string directly to its reversed self
      return cleaned == cleaned[::-1]

  print(is_palindrome("A man a plan a canal Panama"))  # Outputs: True
  print(is_palindrome("Python"))                       # Outputs: False
  ```
  
  </details>

* **What are Data Processing Exercises?**<br>
  **Data processing exercises** involve ingesting raw, unformatted external data logs or structures, sanitizing anomalies, and running data conversions to generate clean informational metrics.

  <details>
  <summary>Click for more</summary>
  
  1. **Pipeline Blueprint:** Follows an **ETL** sequence: Extracting (reading records), Transforming (cleaning missing rows, casting strings to floats), and Loading (computing summaries).
  2. **Defensive Coding:** Safely scrubbing corrupted entries using try-except blocks or inline conditional statements to prevent application failure.
  3. **Real-world Modeling:** Managing rows of text inputs to model business transactions or user login analytics.
  
  **Example Code (Processing Raw Order Log Records):**
  ```python
  raw_orders = [
      {"item": "Laptop", "price": "1200", "status": "shipped"},
      {"item": "Mouse", "price": "N/A", "status": "canceled"},  # Corrupted data
      {"item": "Monitor", "price": "300", "status": "shipped"}
  ]

  def calculate_shipped_total(orders):
      total_revenue = 0.0
      for order in orders:
          if order["status"] == "shipped":
              try:
                  total_revenue += float(order["price"])
              except ValueError:
                  continue  # Skip entry if conversion fails
      return total_revenue

  print(f"Total Revenue: ${calculate_shipped_total(raw_orders)}")  # Outputs: $1500.0
  ```
  
  </details>

* **What is Algorithmic Thinking?**<br>
  **Algorithmic thinking** is the structured step-by-step logic framework used to evaluate performance limitations, breakdown puzzles, and construct the most optimized pathways to solve complex data constraints.

  <details>
  <summary>Click for more</summary>
  
  1. **Big O Notation:** The standardized system metric notation used to estimate how much slower or more memory-intensive an algorithm gets as the data scales up (O(1), O(n), O(n²)).
  2. **Pattern Recognition:** Identifying when a complex problem can be solved by applying a timeless foundational template (such as Binary Search, Two Pointers, or Greedy Strategies).
  3. **Divide and Conquer:** Breaking down single huge computations into nested sub-tasks that resolve progressively.
  
  **Example Code (Binary Search Algorithm - \(O(\log n)\) Time):**
  ```python
  def binary_search(sorted_list, target):
      left = 0
      right = len(sorted_list) - 1
      
      while left <= right:
          mid = (left + right) // 2
          if sorted_list[mid] == target:
              return mid  # Return the index location
          elif sorted_list[mid] < target:
              left = mid + 1   # Discard left half
          else:
              right = mid - 1  # Discard right half
              
      return -1  # Target item not found

  ordered_data = [10, 23, 45, 70, 110, 150]
  print(binary_search(ordered_data, 70))   # Outputs index: 3
  print(binary_search(ordered_data, 99))   # Outputs index: -1
  ```
  
  </details>


---

[◀ Back](.././)