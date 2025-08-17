# Git Assignment - Hero Vired

This repository (`git_assignment_HeroVired`) demonstrates Git workflows, feature branching, bug fixes, Git LFS integration, and collaborative development practices using Python-based calculator programs.

---

## 📌 Q.1: CalculatorPlus Application

### Description
The **CalculatorPlus** application provides basic arithmetic operations:
- Addition
- Subtraction
- Multiplication
- Division  
- Square root (new feature)

### Branch Workflow
1. **Repository Creation**  
   Repository name: `git_assignment_HeroVired`

2. **Branching**  
   - Created branch `dev`
   - Added calculator base code
   - Added new feature `square_root(x)` in branch `feature/sqrt`

3. **Initial Implementation**  

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
        # Bug fix applied later for divide-by-zero
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
```

4. **Bug Fix Implementation (Divide Function)**  

```python
def divide(self, a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero.")
    return a / b
```

5. **Release Flow**
- `dev` merged → `main` → **Release v1.0**
- `feature/sqrt` developed and merged → `dev`
- `dev` merged → `main` → **Release v2.0**

---

## 📌 Q.2: Git LFS Integration

### Steps
1. Installed **Git LFS**  
   ```bash
   git lfs install
   ```

2. Created a new branch `lfs`

3. Tracked large files  
   ```bash
   git lfs track "*.bin"
   git add .gitattributes
   git commit -m "Configured Git LFS for binary files"
   ```

4. Added a file (>200MB)  
   ```bash
   git add large_file.bin
   git commit -m "Added large binary file using Git LFS"
   git push origin lfs
   ```

5. Verified by cloning repository on another machine:
   ```bash
   git clone <repo_url>
   git lfs pull
   ```

---

## 📌 Q.3: Geometry Calculator

### Description
A **Geometry Calculator** that calculates:
- Area of a Circle
- Area of a Rectangle

### Implementation

```python
import math

class GeometryCalculator:

    def calculate_circle_area(self, radius):
        return math.pi * radius ** 2

    def calculate_rectangle_area(self, length, width):
        return length * width

if __name__ == "__main__":
    calculator = GeometryCalculator()

    # Circle Area Example
    radius = 5
    print(f"The area of the circle with radius {radius} = {calculator.calculate_circle_area(radius)}")

    # Rectangle Area Example
    length = 10
    width = 6
    print(f"The area of the rectangle with length {length} and width {width} = {calculator.calculate_rectangle_area(length, width)}")
```

---

### Workflow Steps
1. **Branching**
   - Created `geometry-calculator` branch
   - Created sub-branches:
     - `feature/circle-area`
     - `feature/rectangle-area`

2. **Using Git Stash**
   - While working on circle feature:  
     ```bash
     git stash
     git checkout -b feature/rectangle-area
     ```
   - Later unstashed when switching back:
     ```bash
     git stash pop
     ```

3. **Commit & Push**
   - Completed circle feature → committed & pushed
   - Completed rectangle feature → committed & pushed

4. **Pull Requests**
   - Both feature branches merged into `dev`
   - `dev` tested → merged into `main`

---

## ✅ Deliverables
- **Version 1.0 Release** → Calculator with basic operations  
- **Version 2.0 Release** → Calculator with bug fix + square root feature  
- **Git LFS Branch** → Large file handling using Git LFS  
- **Geometry Calculator** → Features implemented using `git stash` workflow  

---

## 📂 Repository Structure

```
git_assignment_HeroVired/
│
├── calculator_plus.py
├── geometry_calculator.py
├── large_file.bin (tracked by Git LFS)
├── README.md
└── .gitattributes
```

---

## 👥 Collaboration
- Added Deepika Narendran as collaborators.
- Pull requests reviewed & approved before merging.
- Followed proper Git branching strategy (`dev`, `feature/*`, `lfs`, `geometry-calculator`).

---

## 🚀 Conclusion
This project demonstrates:
- Git branching workflows
- Feature development with pull requests
- Bug fixes and hotfix handling
- Git LFS usage
- Collaborative coding practices
- Git stash for managing multiple features
