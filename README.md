# React setInterval Memory Leak
This repository demonstrates a common mistake when using the `setInterval` function within a React component's `useEffect` hook: forgetting to return a cleanup function to clear the interval when the component unmounts.  This leads to a memory leak.

The `bug.js` file contains the problematic code, while `bugSolution.js` provides the corrected version.

## How to Reproduce
1. Clone the repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the count continuously increasing even after navigating away from the component. This indicates the memory leak.

## Solution
The solution involves returning a cleanup function from the `useEffect` hook that uses `clearInterval` to stop the interval when the component unmounts. This prevents the memory leak.