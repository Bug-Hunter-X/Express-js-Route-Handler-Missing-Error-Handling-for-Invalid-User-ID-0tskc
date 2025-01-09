# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of error handling for invalid input parameters.  Specifically, the `/users/:id` route attempts to parse the `id` parameter as an integer. If the parameter is not a valid integer, this will throw an error and crash the application.

## Bug

The `bug.js` file contains the buggy code.  The handler for the `/users/:id` route does not properly handle cases where `req.params.id` is not a valid integer.  This can cause the application to crash.

## Solution

The `bugSolution.js` file provides a corrected version of the code. The solution includes error handling to check if `req.params.id` is a valid integer. If not, it returns an appropriate error response.  It also handles the case where no user is found for the provided ID.

## How to Reproduce

1. Clone this repository.
2. Run `npm install express`
3. Run `node bug.js` and then make a request to `/users/abc` (or any non-numeric value) using a tool like curl or Postman.
4. Compare this to the behavior when running `node bugSolution.js`