# AIND_Constraints_Satisfaction: Solving the N-Queens Problem Using Constraint Satisfaction

## Overview

This project explores the concept of **Constraint Satisfaction Problems (CSP)** in Artificial Intelligence. The goal is to solve the **N-Queens problem** using a symbolic math library, **SymPy**, and the **Backtracking** algorithm. The N-Queens problem involves placing N queens on an N x N chessboard such that no two queens threaten each other. This project applies CSP techniques to solve the N-Queens problem by modeling the problem's constraints explicitly and leveraging backtracking to find solutions.

## Problem Definition

The N-Queens problem asks us to place N queens on an N x N chessboard such that:
1. No two queens share the same row.
2. No two queens share the same column.
3. No two queens share the same diagonal.

This project generalizes the classic 8-Queens problem to N queens on an N x N board, using the symbolic math capabilities of **SymPy** to handle the constraints and recursive **Backtracking** for solution search.

## Steps

### Step 1: Representing the N-Queens Problem
In this step, we represent the N-Queens problem as a **CSP** where:
- Each queen's position is represented by a variable.
- The domain of each variable represents the possible rows where a queen can be placed.
- Constraints ensure that no two queens are placed in the same row or diagonal.

### Step 2: Backtracking Search
Backtracking is used to explore possible assignments of queens to the chessboard. At each step, the algorithm assigns a queen to a row and column while ensuring the constraints are satisfied. If a partial assignment leads to a conflict, the algorithm backtracks and tries different possibilities.

The search uses the following strategies:
- **Minimum Remaining Values (MRV)**: Choose the variable with the fewest legal values to assign next.
- **Forward Checking**: After each assignment, update the domain of the remaining unassigned variables.

### Step 3: Solving the N-Queens Problem
Once the backtracking search algorithm is implemented, the solution is used to solve instances of the N-Queens problem. The algorithm is capable of solving small N values (up to 12 queens) efficiently. For larger values, the solution time increases significantly due to the complexity of the problem.

## Code Walkthrough

### Symbolic Constraints

The problem uses symbolic constraints defined using **SymPy**:
- **diffRow**: Ensures that no two queens are placed in the same row.
- **diffDiag**: Ensures that no two queens are placed on the same diagonal.

### NQueensCSP Class

The core of the project is the `NQueensCSP` class, which models the N-Queens problem as a CSP. It provides methods to check for consistency and completeness, perform inference, and display the solution.

### Backtracking Search

The backtracking search uses recursive methods to explore all possible assignments of queens while respecting the constraints. The algorithm uses heuristics to make the search more efficient and avoid unnecessary exploration.

### Map Coloring Example

In addition to the N-Queens problem, a map coloring example is also included. This example demonstrates how constraints can be applied to a map coloring problem where regions must be assigned different colors.

## Dependencies

This project uses the following Python libraries:
- **SymPy**: A Python library for symbolic mathematics.
- **Matplotlib**: Used to display the solution visually.
- **IPython**: For interactive display of symbolic expressions.

To install the dependencies, run:

```bash
pip install sympy matplotlib ipython
```bash

## Usage
To solve the N-Queens problem, run the main.py script. It will solve the problem for a 5x5 board by default, but you can modify the num_queens variable to change the board size.

### Example:
```bash
python
Copy code
num_queens = 5
csp = NQueensCSP(num_queens)
solution = backtracking_search(csp)
if solution:
    csp.show(solution)
else:
    print("No solution found.")
```bash

## Output
The solution will be displayed as a chessboard with queens placed in valid positions. For example, a solution for a 5x5 board might look like this:

```bash
Solution found:
{col0: 0, col1: 2, col2: 4, col3: 1, col4: 3}
```bash

## Conclusion
This project demonstrates the power of Constraint Satisfaction in solving problems like the N-Queens puzzle. By using symbolic math to define constraints and backtracking for searching, we can efficiently find solutions to problems with multiple variables and complex constraints.
