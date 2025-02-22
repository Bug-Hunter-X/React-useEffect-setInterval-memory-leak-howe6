# React useEffect setInterval memory leak

This repository demonstrates a common mistake in React applications: using `setInterval` within a `useEffect` hook without proper cleanup. This leads to a memory leak as the interval continues to run even after the component unmounts.

The `bug.js` file contains the problematic code. The `bugSolution.js` file shows the corrected version.

## Bug
The bug is caused by using `setInterval` inside the `useEffect` hook without specifying a cleanup function.  This function is crucial for stopping the interval when the component unmounts, preventing the memory leak.

## Solution
The solution involves returning a cleanup function from the `useEffect` hook. This function will clear the interval when the component is unmounted, freeing up resources and preventing the memory leak.