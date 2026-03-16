---
name: cp-skills-cpp
description: A structured competitive programming knowledge base focused on algorithmic thinking, data structures, and high-performance C++ implementations.
license: MIT
metadata:
  - author: area44
  - version: "26.03.06"
---

# Competitive Programming Skills

A structured and efficiency-driven knowledge base for mastering competitive programming. This repository emphasizes algorithmic reasoning, core data structures, implementation patterns, and writing optimized C++23 code under contest constraints.

## Objectives

- Develop strong algorithmic intuition.
- Build clean and minimal implementation habits.
- Maintain high-performance coding discipline.
- Improve speed and accuracy under time pressure.

# Language & Coding Standards

## Language Standard

- Use **C++23**.

## Code Style Guidelines

### Minimalism First

- Do not include comments in final submission code.
- Avoid unnecessary abstractions.
  - Do not create a `solve()` function if the logic fits clearly inside `main()`.

- Avoid unnecessary variables.
  - Do not store intermediate results if they are used only once.

## Naming & Structure Guidelines

### Variables

- Use `camelCase`.
- Keep names simple, clear, and descriptive.

### Functions

- Use `snake_case`.
- Function names must begin with a verb.
- Clearly describe the action performed.

### Constants

- Use `ALL_CAPS` with underscores.

### Code Structure

- Keep logic linear and readable.
- Avoid deep nesting when possible.
- Prefer early returns to reduce indentation.
- Minimize global variables (allowed only for constants and large shared arrays).

### Struct Usage

- Do **not** use `struct` unless it meaningfully improves clarity or groups logically inseparable data.

Avoid `struct` when:

- The data is used only locally inside a small algorithm.
- A simple `vector`, `pair`, or separate arrays are sufficient.
- The structure is used only once.

Prefer simpler alternatives:

- Use `pair` or `tuple` for small grouped values.
- Use parallel `vector`s when processing large datasets.
- Keep related variables close in scope instead of wrapping them in a `struct`.

Use `struct` only when:

- Multiple fields must travel together across functions.
- The structure represents a clear logical entity (e.g., graph edge, query, event).
- It significantly improves readability in large implementations.

Example (avoid unnecessary struct):

```cpp
// Avoid
struct Node {
  int l, r, value;
};

// Prefer
vector<int> leftChild, rightChild, value;
```

## Loop Preferences

- Prefer range-based loops.
  - Use `for (auto &x : container)` when modifying elements or avoiding copies.
  - Use `for (auto x : container)` for read-only access.

## STL Discipline

- Prefer `vector` over `array`.
- Prefer `vector` over `set` or `map` unless ordering or logarithmic operations are required.
- Prefer `sort()` over maintaining dynamically ordered containers.
- Avoid `multiset` unless strictly necessary.
- Use `reserve()` when size is known in advance.
- Prefer `emplace_back()` for in-place construction.
- Avoid unnecessary copying of large structures.
  - Prefer `const vector<int>&` over `vector<int>` when passing arguments.

## I/O Rules

- Use `cin` and `cout`.
- Disable synchronization:

```cpp
ios::sync_with_stdio(false);
cin.tie(nullptr);
```

- Use `"\n"` instead of `endl`.

# Performance Discipline

- Estimate time complexity before coding.
- Target complexity guidelines:
  - `O(n)` or `O(n log n)` for `n ≤ 2e5`
  - `O(n^2)` only if `n ≤ 2000`
  - `O(2^n)` only if `n ≤ 20`

- Preallocate memory when possible.
- Avoid resizing containers inside loops.
- Use static arrays when size is fixed and performance-critical.

# Compilation Template

```cpp
#include <bits/stdc++.h>
using namespace std;

using ll = long long;
using ull = unsigned long long;
using i128 = __int128_t;

constexpr ll INF = LLONG_MAX;
constexpr int MOD = 998244353;

int main() {
  ios::sync_with_stdio(false);
  cin.tie(nullptr);

  return 0;
}
```

# Competitive Programming Philosophy

Competitive programming requires:

- Careful constraint analysis.
- Strong pattern recognition.
- Transforming brute force into structured logic.
- Writing correct code quickly under pressure.

Clarity over cleverness. Performance over abstraction. Correctness over style.

Build intuition. Remove noise. Optimize thinking.
