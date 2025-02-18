# Express.js Route Handler Error

This repository demonstrates a common error in Express.js route handlers:  lack of error handling for invalid input.  Specifically, the `/users/:id` route fails to gracefully handle cases where `req.params.id` is not a valid integer. 

The `bug.js` file shows the erroneous code.  The `bugSolution.js` file provides a corrected version with appropriate error handling.

## How to Reproduce

1. Clone this repository.
2. Run `npm install express`.
3. Run `node bug.js`.
4. Send a GET request to `/users/abc` (or any non-numeric ID).  You'll see an error.

## Solution

The solution involves adding error handling to check if `parseInt(userId)` produces a valid integer and handling the case where a user is not found.