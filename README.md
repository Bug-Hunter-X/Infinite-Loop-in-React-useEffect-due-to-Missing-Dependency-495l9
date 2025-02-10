# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook.  The bug arises from incorrectly specifying the dependency array, leading to an infinite loop.

## Bug Description

The `useEffect` hook is used to perform side effects after a component renders. When the dependency array is missing or incorrect, the effect runs on every render, often causing infinite re-renders and crashing the application. In this example, missing `count` from the dependency array results in an infinite loop.

## Solution

The solution involves correctly specifying the dependency array in the `useEffect` hook.  The dependency array should include all variables from the component's scope that the effect depends on. If the effect doesn't depend on any component state or props, the dependency array should be an empty array: `[]`.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the infinite loop in the console and potential crashing of the browser.

## How to Fix

Examine the provided solution (`bugSolution.js`). The fix involves adding `count` to the dependency array within `useEffect`. This ensures the effect only runs when the value of `count` changes.