# React useEffect Hook Memory Leak

This repository demonstrates a common error in React applications: memory leaks caused by missing cleanup functions within the `useEffect` hook.  The `bug.js` file shows the problematic code, while `bugSolution.js` provides the corrected version.

The issue arises from the `setInterval` function within `useEffect`. Without a cleanup function, the interval continues to run even after the component unmounts, leading to memory leaks. This is especially problematic in applications with many components using this pattern.

The solution involves using the return value of `useEffect` to provide a cleanup function that clears the interval before the component unmounts.