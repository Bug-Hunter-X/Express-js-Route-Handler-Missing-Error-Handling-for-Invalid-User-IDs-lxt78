# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers: the lack of error handling for invalid input, specifically non-numeric user IDs in this case.

## Bug
The `bug.js` file contains an Express.js route handler that fetches a user by ID.  It attempts to parse the ID as an integer without verifying if the input is numeric.  If a non-numeric ID is provided, `parseInt(userId)` will return `NaN`, leading to the `users.find()` method potentially failing silently or throwing an error.

## Solution
The `bugSolution.js` file provides a corrected version of the route handler. It includes input validation to check if `userId` can be parsed as an integer before proceeding. If the ID is invalid, an appropriate error response is returned.