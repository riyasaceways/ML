[◀ Back to Index](../../../../../../README.md) &emsp; | &emsp;[◀ Back](./)

---

# Apply Through Hands-on Tasks — Requirements & Commands

The purpose of this task is to move from **understanding ML concepts to actually applying them**. Each section should produce some practical evidence that can be documented in the GitHub repository.

---

## a. Set up ML development environment

**Need:** Create a working environment for developing and testing ML programs.

### Requirements

* Install Python.
* Create an ML project folder.
* Create a virtual environment.
* Activate the environment.
* Install basic ML packages.
* Install Jupyter Notebook and `ipykernel`.
* Register the environment as a Jupyter kernel.
* Verify that the packages work.
* Run a simple ML environment test.

### Commands

Create/open the project:

```cmd
cd C:\Users\Riyas\PythonStudy
```

Create the virtual environment:

```cmd
py -m venv .venv
```

Activate it:

```cmd
.venv\Scripts\activate
```

Verify Python:

```cmd
python --version
```

Install the required packages:

```cmd
python -m pip install numpy pandas matplotlib scikit-learn jupyter ipykernel
```

Verify the ML packages:

```cmd
python -c "import numpy, pandas, matplotlib, sklearn; print('All ML packages are working')"
```

Register the environment with Jupyter:

```cmd
python -m ipykernel install --user --name pythonstudy --display-name "PythonStudy (.venv)"
```

Start Jupyter:

```cmd
jupyter notebook
```

Then select:

```text
PythonStudy (.venv)
```

### Notebook verification

Create a notebook such as:

```text
ml_environment_test.ipynb
```

Run:

```python
import sys
import numpy
import pandas
import matplotlib
import sklearn

print("Python:", sys.version)
print("Executable:", sys.executable)
print("ML environment is working!")
```

**Result:** A working ML development environment with Python, virtual environment, ML libraries, and Jupyter.

---

# b. Explore sample datasets

**Need:** Get practical experience working with datasets.

### Requirements

* Obtain a sample dataset.
* Load it using pandas.
* View the data.
* Understand its rows and columns.
* Check its size.
* Identify features and possible labels.
* Check for missing values.
* Perform basic exploration.

### Useful commands

Install/use pandas:

```cmd
python -m pip install pandas
```

Inside Jupyter:

```python
import pandas as pd
```

Load a CSV:

```python
df = pd.read_csv("sample_dataset.csv")
```

View the first rows:

```python
df.head()
```

Check the dataset size:

```python
df.shape
```

Check column names:

```python
df.columns
```

Check data types:

```python
df.info()
```

Check basic statistics:

```python
df.describe()
```

Check missing values:

```python
df.isnull().sum()
```

### Result

A notebook showing the dataset and basic observations about its structure and quality.

---

# c. Analyze real-world ML applications

**Need:** Understand how ML is actually used to solve real-world problems.

Choose several applications, for example:

* Fraud detection
* Recommendation systems
* Spam detection
* Image classification
* Customer churn prediction
* Demand prediction

For each application, document:

```text
Problem
↓
Data
↓
Features / Inputs
↓
ML Model
↓
Prediction / Output
↓
Practical Use
```

### Example

**Fraud Detection**

```text
Problem:
Identify potentially fraudulent transactions.

Data:
Transaction history.

Features:
Transaction amount, location, time, transaction frequency, etc.

Model:
Classification model.

Output:
Fraud / Not Fraud.

Use:
Help detect suspicious transactions.
```

### Result

A document containing several real-world ML applications and how ML contributes to each one.

---

# d. Document ML lifecycle for a chosen problem

**Need:** Apply the ML lifecycle to one specific problem.

Choose one problem, for example:

> Predict whether a customer will leave a service.

Document each stage:

```text
Data Collection
      ↓
Data Preparation
      ↓
Model Training
      ↓
Model Evaluation
      ↓
Model Deployment
      ↓
Continuous Improvement
```

### What to document

**1. Data Collection**

Where would the data come from?

**2. Data Preparation**

How would the data be cleaned and prepared?

**3. Model Training**

What would the model learn from?

**4. Model Evaluation**

How would you determine whether the model performs well?

**5. Model Deployment**

Where would the trained model be used?

**6. Continuous Improvement**

How would the model be monitored and updated?

### Result

A complete ML lifecycle document for one chosen problem.

---

# e. Compare traditional software vs ML systems

**Need:** Understand how ML development differs from traditional software development.

Create a comparison such as:

| Traditional Software                        | ML System                               |
| ------------------------------------------- | --------------------------------------- |
| Rules are explicitly programmed             | Patterns are learned from data          |
| Behavior mainly comes from code             | Behavior depends on model and data      |
| Code changes commonly modify behavior       | New data/retraining can modify behavior |
| Testing focuses heavily on programmed logic | Testing also measures model performance |
| Data is usually an input                    | Data is essential for training          |

### Practical task

Choose one simple problem and describe how it could be solved both ways.

For example:

**Traditional software:**

```text
IF temperature > 30
THEN display "Hot"
```

**ML system:**

```text
Temperature + other observations
              ↓
          ML model
              ↓
       Predicted condition
```

### Result

A written comparison showing the difference between traditional software and ML systems.

---

# f. Use AI to explain an ML workflow and validate its explanation

**Need:** Use AI as a learning assistant while checking whether its explanation is actually correct.

### Steps

**1. Ask AI**

For example:

> Explain the complete machine learning lifecycle for a beginner using a simple real-world example.

**2. Save the AI explanation.**

**3. Validate it**

Compare the explanation with your ML course material and notes.

Check:

* Are all lifecycle stages included?
* Is the order reasonable?
* Are the explanations technically correct?
* Is anything important missing?
* Did the AI make any incorrect claims?

**4. Correct the explanation**

Document corrections where necessary.

### Result

A document containing:

```text
AI Question
     ↓
AI Explanation
     ↓
Validation
     ↓
Problems Found
     ↓
Corrections
     ↓
Final Understanding
```

This demonstrates that AI was used for learning **without blindly trusting its output**.

---

# Final Hands-on Evidence

By the end of this task, your repository should ideally contain evidence for:

```text
01. ML Development Environment
    ├── Python installed
    ├── .venv created
    ├── ML packages installed
    ├── Jupyter configured
    └── Environment test notebook

02. Sample Dataset Exploration
    └── Dataset exploration notebook

03. Real-world ML Applications
    └── Application analysis document

04. ML Lifecycle
    └── Chosen problem + lifecycle documentation

05. Traditional Software vs ML
    └── Comparison document

06. AI-assisted ML Workflow
    └── AI explanation + validation
```

The important point is that **you don't need to build a sophisticated ML model yet**. This task is mainly about setting up the environment, working with data, connecting ML concepts to real problems, and demonstrating that you can follow and validate an ML workflow.

---

[◀ Back to Index](../../../../../../README.md) &emsp; | &emsp;[◀ Back](./)