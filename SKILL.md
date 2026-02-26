---
name: cp-skills
description: A structured competitive programming knowledge base focused on algorithmic thinking, data structures, and high-performance C++ implementations.
license: MIT
metadata:
  - author: area44
  - version: "2026.02.26"
---

# Competitive Programming Skills

A structured and performance-oriented knowledge base for mastering competitive programming.
This repository focuses on algorithmic thinking, data structures, implementation patterns, and writing efficient C++23 code under contest constraints.

The goal is to build:

- Strong algorithmic intuition.
- Clean and minimal implementation habits.
- High-performance coding discipline.
- Fast and accurate problem-solving skills.

# Language & Coding Standards

## Language Standard

- Use **C++23**.

## Code Style Guidelines

### Minimalism First

- Do not include comments in final submission code.
- Avoid unnecessary abstractions.
  - Do not create a `solve()` function if everything fits clearly inside `main()`.
- Avoid unnecessary variables.
  - Do not store intermediate values if they are used only once.
  - Example prefer:
    ```cpp
    cout << b + c << "\n";
    ```
    instead of:
    ```cpp
    int a = b + c;
    cout << a << "\n";
    ```

### Naming & Structure

- Use simple variable names.
  - Prefer `var_a` over `varA`.
- Keep logic linear and readable.
- Avoid deep nesting when possible.
- Prefer early returns to reduce indentation.
- Minimize global variables (except constants and large arrays).

### Loop Preferences

- Prefer range-based loops.
  - Use `for (auto &x : container)` when modifying elements or avoiding copies.
  - Use `for (auto x : container)` when working with read-only values.

### STL Discipline

- Prefer `vector` over `array`.
- Prefer `vector` over `set` / `map` unless ordered or logarithmic operations are required.
- Prefer `sort()` over dynamically maintaining ordered containers.
- Avoid `multiset` unless strictly necessary.
- Use `reserve()` when size is known in advance.
- Prefer `emplace_back()` when constructing elements in-place.
- Avoid unnecessary copying of large structures.
  - Prefer `const vector<int>&` over `vector<int>` when passing arguments.

### I/O Rules

- Use `cin` and `cout`.
- Disable synchronization:
  ```cpp
  ios::sync_with_stdio(false);
  cin.tie(nullptr);
  ```
- Use `"\n"` instead of `endl`.

# Performance Discipline

- Always estimate time complexity before coding.
- Target complexity guidelines:
  - `O(n)` or `O(n log n)` for `n ≤ 2e5`
  - `O(n^2)` only if `n ≤ 2000`
  - `O(2^n)` only if `n ≤ 20`
- Preallocate memory when possible.
- Avoid resizing containers inside loops.
- Use static arrays when size is fixed and performance is critical.

# Compilation Template

```cpp
#include <bits/stdc++.h>
using namespace std;

using ll = long long;
using i128 = __int128_t;

constexpr ll INF = 4e18;
constexpr int MOD = 1e9 + 7;

int main() {
  ios::sync_with_stdio(false);
  cin.tie(nullptr);

  return 0;
}
```

# Competitive Programming Philosophy

Competitive programming is about:

- Constraint analysis.
- Pattern recognition.
- Reducing brute force into structured logic.
- Writing correct code quickly under pressure.

Clarity > cleverness.
Performance > abstraction.
Correctness > style.

Build intuition. Eliminate noise. Optimize thinking.
