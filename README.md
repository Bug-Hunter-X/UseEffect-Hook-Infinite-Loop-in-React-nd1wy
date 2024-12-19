# useEffect Hook Infinite Loop in React

This repository demonstrates a common error in React's `useEffect` hook: an infinite loop caused by a missing dependency.  The `bug.js` file contains the erroneous code, while `bugSolution.js` provides the corrected version.

## Problem

The `useEffect` hook in `bug.js` logs the current count to the console. However, because it lacks the `count` variable in its dependency array, it runs after *every* render, leading to an infinite loop and potentially crashing the browser. This is especially problematic if the effect performs computationally expensive tasks.

## Solution

`bugSolution.js` fixes the issue by including `count` in the dependency array: `[count]`. This ensures that the effect only re-runs when the value of `count` changes.