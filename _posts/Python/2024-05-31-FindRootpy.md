---
layout: post
title: "[Python] Find root"
excerpt: "방정식의 해를 구하는 법"
category: Python
tags: [python]
comments: false
---
```py
import math

def newton_method(f, df, x0, tol=1e-6, max_iter=1000):
    x = x0
    for _ in range(max_iter):
        fx = f(x)
        dfx = df(x)
        if dfx == 0:
            raise ValueError("Derivative is zero. No solution found.")
        x_new = x - fx / dfx
        if abs(x_new - x) < tol:
            return x_new
        x = x_new
    raise ValueError("Exceeded maximum iterations. No solution found.")

# Constants
A = 2  # Example value for A
B = 1  # Example value for B
C = 3  # Example value for C

# Function and its derivative
f = lambda x: A * x + B * math.sin(x) - C
df = lambda x: A + B * math.cos(x)

# Initial guess
x0 = 1.0  # Example initial guess

# Finding the root
try:
    root = newton_method(f, df, x0)
    print("Root:", root)
except ValueError as e:
    print(e)
```

시각화한 코드
```py
import numpy as np
import matplotlib.pyplot as plt

# Constants
A = 2  # Example value for A
B = 1  # Example value for B
C = 3  # Example value for C

# Function and its derivative
f = lambda x: A * x + B * np.sin(x) - C
df = lambda x: A + B * np.cos(x)

# Newton's method
def newton_method(f, df, x0, tol=1e-6, max_iter=1000):
    x = x0
    for _ in range(max_iter):
        fx = f(x)
        dfx = df(x)
        if dfx == 0:
            raise ValueError("Derivative is zero. No solution found.")
        x_new = x - fx / dfx
        if abs(x_new - x) < tol:
            return x_new
        x = x_new
    raise ValueError("Exceeded maximum iterations. No solution found.")

# Initial guess
x0 = 1.0  # Example initial guess

# Finding the root
try:
    root = newton_method(f, df, x0)
    print("Root:", root)
except ValueError as e:
    print(e)

# Plotting the function and the root
x_values = np.linspace(-10, 10, 400)
y_values = f(x_values)

plt.figure(figsize=(10, 6))
plt.plot(x_values, y_values, label=f'{A}x + {B}sin(x) - {C}')
plt.axhline(0, color='black', linewidth=0.5)
plt.axvline(root, color='red', linestyle='--', label=f'Root at x = {root:.4f}')
plt.scatter(root, f(root), color='red')  # Mark the root
plt.title('Graph of the function and its root')
plt.xlabel('x')
plt.ylabel('f(x)')
plt.legend()
plt.grid(True)
plt.show()
```

