# React useEffect Cleanup Function Inconsistency

This repository demonstrates a common error in React's `useEffect` hook: neglecting to handle component unmounts properly within the cleanup function.

The `bug.js` file showcases the problem. The cleanup function (`return () => { ... }`) within the `useEffect` is only executed when the component initially mounts. This means that any side effects started within `useEffect` won't be cleaned up when the component unmounts, leading to potential memory leaks and unexpected behavior.

The `bugSolution.js` file provides the corrected version. The cleanup function is now always executed before the component is unmounted, ensuring that cleanup actions happen reliably.

## How to Reproduce
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the console logs during component mounting and unmounting in both `bug.js` and `bugSolution.js` to see the difference.