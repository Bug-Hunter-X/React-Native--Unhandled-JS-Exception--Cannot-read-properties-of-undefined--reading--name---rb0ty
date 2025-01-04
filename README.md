# React Native: Accessing State Before Assignment

This repository demonstrates a common error in React Native applications: attempting to access state or props before they've been initialized. This often results in an `undefined is not an object` or similar error.

## The Problem

The `bug.js` file showcases the problematic code.  The component tries to render data from the `this.state.data` before the asynchronous `fetch` call in `componentDidMount` completes. This leads to an error because `this.state.data` is initially `null`.

## The Solution

The `bugSolution.js` file provides a solution. It uses conditional rendering to only render the data once it's been fetched and assigned to the state. This prevents errors by avoiding access before initialization.  Alternatively, optional chaining (`?.`) can be used as a shorter approach.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` or `yarn install`.
3. Run the application using your preferred React Native method. You will see the error in the original code.
4. Switch to the `bugSolution.js` to see the fix in action.

This example highlights the importance of handling asynchronous operations and carefully considering the timing of state access in React Native components.