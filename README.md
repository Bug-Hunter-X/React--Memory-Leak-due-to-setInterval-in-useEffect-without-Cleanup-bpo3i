# React: Memory Leak due to setInterval in useEffect without Cleanup

This repository demonstrates a common React bug: memory leaks caused by the improper use of `setInterval` within the `useEffect` hook without a cleanup function.  The example shows a simple counter component that increments every second. However, because the `setInterval` is not properly cleaned up when the component unmounts, it continues to run in the background, leading to a memory leak.

## Problem

The `setInterval` function, if not stopped when the component is unmounted, will keep running indefinitely. This causes the component to retain references to previous states, eventually leading to memory exhaustion. 

## Solution

The solution is to use the cleanup function provided by the `useEffect` hook to clear the interval when the component is unmounted or when the dependencies change.

## How to reproduce
1. Clone the repository.
2. Install dependencies: `npm install`
3. Run the app: `npm start`
4. Open your browser and observe the counter.
5. Unmount the component (e.g., navigate to a different page) and observe that the setInterval continues to run.