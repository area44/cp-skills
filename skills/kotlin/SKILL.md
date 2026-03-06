---
name: cp-skills-kotlin
description: A structured competitive programming knowledge base focused on algorithmic thinking, data structures, and high-performance Kotlin implementations.
license: MIT
metadata:
  - author: area44
  - version: "26.03.06"
---

# Competitive Programming Skills (Kotlin Edition)

A structured and efficiency-driven knowledge base for mastering competitive programming using Kotlin.
This repository emphasizes algorithmic reasoning, core data structures, implementation patterns, and writing optimized Kotlin code under contest constraints.

# Objectives

- Develop strong algorithmic intuition.
- Build clean and minimal implementation habits.
- Maintain high-performance coding discipline.
- Improve speed and accuracy under time pressure.

# Language & Coding Standards

## Language Standard

- Use **Kotlin (JVM)**.
- Prefer latest stable Kotlin version allowed by the judge.
- Target JVM 17+ when possible.

# Code Style Guidelines

## Minimalism First

- Do not include comments in final submission code.
- Avoid unnecessary abstractions.
  - Do not create extra functions if logic fits clearly inside `main()`.
- Avoid unnecessary variables.
  - Do not store intermediate results if they are used only once.

# Naming & Structure Guidelines

## Variables

- Use `camelCase`.
- Keep names simple, clear, and descriptive.

## Functions

- Use `snake_case`.
- Function names must begin with a verb.
- Clearly describe the action performed.

## Constants

- Use `UPPER_CASE_WITH_UNDERSCORES`.
- Prefer `const val` for compile-time constants.

# Code Structure

- Keep logic linear and readable.
- Avoid deep nesting.
- Prefer early returns.
- Minimize global variables (allowed only for constants or large shared arrays).

# Loop Preferences

- Prefer `repeat(n)` when index not needed.
- Prefer `for (i in 0 until n)` for index-based loops.
- Prefer direct iteration:

```kotlin
for (x in list)
```

- Avoid unnecessary higher-order functions (`map`, `filter`) in tight loops.

# Collection Discipline

- Prefer `IntArray`, `LongArray` over `Array<Int>` for performance.
- Prefer arrays over lists in performance-critical sections.
- Prefer `MutableList` only when dynamic resizing is required.
- Prefer sorting via:

```kotlin
array.sort()
```

- Avoid `sorted()` (creates copy).
- Avoid `HashMap`/`HashSet` unless necessary.
- Prefer arrays for frequency counting when bounds are known.
- Preallocate with:

```kotlin
val arr = IntArray(n)
```

- Avoid resizing inside loops.

# I/O Rules (CRITICAL FOR KOTLIN)

Default Kotlin I/O is too slow for competitive programming.

## Fast I/O Template

Use `BufferedReader` and `PrintWriter`.

```kotlin
import java.io.BufferedReader
import java.io.InputStreamReader
import java.io.PrintWriter
import java.util.StringTokenizer

fun main() {
    val br = BufferedReader(InputStreamReader(System.`in`))
    val out = PrintWriter(System.out)

    out.flush()
}
```

### Reading Integers Fast

```kotlin
val st = StringTokenizer(br.readLine())
val x = st.nextToken().toInt()
```

Avoid:

- `readLine()!!.split(" ")`
- `Scanner`

# Performance Discipline

Always estimate time complexity before coding.

## Target Complexity Guidelines

- `O(n)` or `O(n log n)` for `n ≤ 2e5`
- `O(n^2)` only if `n ≤ 2000`
- `O(2^n)` only if `n ≤ 20`

## Performance Rules Specific to Kotlin

- Prefer `IntArray` over `MutableList<Int>`.
- Avoid boxing (`Int?`, `List<Int>` in hot paths).
- Avoid recursion (stack overflow risk).
- Avoid lambdas in tight loops.
- Avoid sequence APIs (`asSequence()`).
- Use `StringBuilder` if constructing large output.
- Use `repeat(t)` instead of `for (i in 0 until t)` when index unused.
- Use primitive math (`kotlin.math`) only when needed.

# Kotlin Compilation Template

```kotlin
import java.io.BufferedReader
import java.io.InputStreamReader
import java.io.PrintWriter
import java.util.StringTokenizer

private const val INF = Long.MAX_VALUE
private const val MOD = 1_000_000_007

fun main() {
    val br = BufferedReader(InputStreamReader(System.`in`))
    val out = PrintWriter(System.out)

    out.flush()
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
