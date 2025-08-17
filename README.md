# Git Assignment - HeroVired  

This project demonstrates practical usage of **Git**, **branching strategies**, **Git LFS**, and **Git stash** in a DevOps workflow.  
It includes a Python-based **CalculatorPlus** application and a **Geometry Calculator** with proper Git workflows.  

---

## 📌 Project Overview  

- **Repository:** `git_assignment_HeroVired`  
- **Main Features:**  
  - CalculatorPlus (Basic arithmetic + Square Root feature)  
  - Geometry Calculator (Circle & Rectangle area)  
  - Git LFS for handling large files (>200MB)  
  - Git stash to manage incomplete work between features  

---

## 🛠️ Features Implemented  

### 1. CalculatorPlus  

File: `calculator_plus.py`  

```python
import math

class Calculator:

    def add(self, a, b):
        return a + b

    def subtract(self, a, b):
        return a - b

    def multiply(self, a, b):
        return a * b

    def divide(self, a, b):
        if b == 0:
            raise ValueError("Cannot divide by zero.")
        return a / b

    def square_root(self, x):
        return math.sqrt(x)


if __name__ == "__main__":
    calculator = Calculator()

    num1 = 16
    num2 = 4

    print(f"{num1} + {num2} = {calculator.add(num1, num2)}")
    print(f"{num1} - {num2} = {calculator.subtract(num1, num2)}")
    print(f"{num1} * {num2} = {calculator.multiply(num1, num2)}")
    print(f"{num1} / {num2} = {calculator.divide(num1, num2)}")

    num3 = 25
    print(f"The square root of {num3} = {calculator.square_root(num3)}")

✅ Example Output
<img width="1138" height="165" alt="image" src="https://github.com/user-attachments/assets/d59cf1a1-f424-4557-802b-448e19e04f67" />

📌 Project Overview

Repository: git_assignment_HeroVired

Main Features:

CalculatorPlus (Basic arithmetic + Square Root feature)

Geometry Calculator (Circle & Rectangle area)

Git LFS for handling large files (>200MB)

Git stash to manage incomplete work between features
