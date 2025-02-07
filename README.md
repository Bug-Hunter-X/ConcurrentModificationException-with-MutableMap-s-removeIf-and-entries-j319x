# Kotlin ConcurrentModificationException with MutableMap and removeIf
This repository demonstrates a subtle difference in behavior between `removeIf` when used with `MutableList` and `MutableMap` in Kotlin.  Specifically, iterating through a `MutableMap`'s entries using `entries` and modifying the map simultaneously using `removeIf` results in a `ConcurrentModificationException`.

The provided code showcases this issue and its resolution.

## Bug
The `bug.kt` file contains code that reproduces the `ConcurrentModificationException`.  It illustrates how `removeIf` works correctly with `MutableList`, but throws an exception when used with the `entries` of a `MutableMap`.

## Solution
The `bugSolution.kt` file demonstrates a safe way to remove elements from a `MutableMap` while iterating using `entries`.  It uses an iterator and its `remove()` method to avoid the concurrent modification problem.