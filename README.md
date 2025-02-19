# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  Specifically, the provided code lacks error handling for non-numeric user IDs in a route parameter.

## Bug

The `bug.js` file contains an Express.js route handler that fetches a user by ID.  It attempts to parse the ID from the request parameters as an integer using `parseInt()`. However, it doesn't check if the parsed value is actually a number. If a non-numeric ID is passed, `parseInt()` will return `NaN`, leading to a potential crash or unexpected behavior when searching the `users` array.

## Solution

The `bugSolution.js` file shows the corrected code with proper error handling. Before attempting to parse the ID, it checks if it's a valid number using `isNaN()`. If the ID is not a valid number, an appropriate error response is returned.

## How to Run

1. Clone the repository.
2. Navigate to the repository's directory.
3. Run `npm install` to install the required dependencies.
4. Run `node bug.js` or `node bugSolution.js` to test the buggy and fixed versions, respectively.