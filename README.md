# Stale Closures in React's useEffect Hook

This repository demonstrates a common error in React applications involving stale closures within the `useEffect` hook.  The example shows how using a closure over a state variable can lead to unexpected behavior if not handled correctly.

## The Bug
The `bug.js` file contains a component that attempts to increment a counter every second using `setInterval` within a `useEffect` hook. The problem lies in how the `count` variable is used inside the `setInterval` callback. Because this refers to the value of count when useEffect is first called.  The counter doesn't update as expected. 

## The Solution
The `bugSolution.js` file demonstrates the correct approach, using the functional update pattern to access the latest value of the state variable.