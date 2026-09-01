[◀ Back to Index](../../../../../README.md) &emsp; | &emsp;[◀ Back](./)

---

# ML Development Environment Setup — Command List

Run these commands **in this order** from:

```cmd
C:\Users\Riyas\PythonStudy
```

### 1. Create the virtual environment

```cmd
py -m venv .venv
```

### 2. Activate the virtual environment

```cmd
.venv\Scripts\activate
```

You should see:

```text
(.venv) C:\Users\Riyas\PythonStudy>
```

### 3. Verify Python

```cmd
python --version
```

Expected:

```text
Python 3.14.7
```

### 4. Install ML packages + Jupyter

```cmd
python -m pip install numpy pandas matplotlib scikit-learn jupyter ipykernel
```

Installed packages:

* `numpy`
* `pandas`
* `matplotlib`
* `scikit-learn`
* `jupyter`
* `ipykernel`

### 5. Verify the ML packages

```cmd
python -c "import numpy, pandas, matplotlib, sklearn; print('All ML packages are working')"
```

Expected:

```text
All ML packages are working
```

### 6. Make sure `ipykernel` is installed

```cmd
python -m pip install ipykernel
```

If it is already installed, you'll see:

```text
Requirement already satisfied
```

That's fine.

### 7. Register the virtual environment with Jupyter

```cmd
python -m ipykernel install --user --name pythonstudy --display-name "PythonStudy (.venv)"
```

Expected:

```text
Installed kernelspec pythonstudy in ...
```

### 8. Start Jupyter Notebook

```cmd
jupyter notebook
```

### 9. Select the correct kernel

Inside Jupyter, select:

```text
PythonStudy (.venv)
```

**Do not select a generic `Python 3` kernel.**

### 10. Verify everything inside the notebook

Run this in a notebook cell:

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

The `Executable` path should point somewhere inside:

```text
C:\Users\Riyas\PythonStudy\.venv\
```

---

## Clean setup flow

```text
Python Install Manager
        ↓
Python 3.14.7
        ↓
PythonStudy
        ↓
.venv
        ↓
Activate .venv
        ↓
numpy
pandas
matplotlib
scikit-learn
        ↓
Jupyter + ipykernel
        ↓
PythonStudy (.venv) kernel
        ↓
Jupyter Notebook
```

### If starting completely fresh

The essential command sequence is:

```cmd
cd C:\Users\Riyas\PythonStudy
py -m venv .venv
.venv\Scripts\activate
python --version
python -m pip install numpy pandas matplotlib scikit-learn jupyter ipykernel
python -c "import numpy, pandas, matplotlib, sklearn; print('All ML packages are working')"
python -m ipykernel install --user --name pythonstudy --display-name "PythonStudy (.venv)"
jupyter notebook
```

This is the command sequence you can keep in your ML setup documentation.


___


[◀ Back to Index](../../../../../README.md) &emsp; | &emsp;[◀ Back](./)