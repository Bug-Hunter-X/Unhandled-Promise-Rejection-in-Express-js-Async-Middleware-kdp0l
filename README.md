# Unhandled Promise Rejection in Express.js Async Middleware

This repository demonstrates a common error in Express.js applications: unhandled promise rejections in asynchronous middleware.  When an asynchronous operation within a route handler throws an error and isn't properly caught, the application can crash unexpectedly.

The `bug.js` file showcases this issue.  The `someAsyncOperation` function simulates an asynchronous task that throws an error. The error is logged to the console, but no mechanism is in place to send an appropriate error response to the client or gracefully handle the failure, leading to a server crash.

The solution, provided in `bugSolution.js`, demonstrates how to correctly handle such errors using a `try...catch` block within the async function or using the `.catch()` method to handle errors properly.  This prevents the application from crashing and allows for sending a proper error response to the client.

## How to Reproduce

1. Clone this repository.
2. Navigate to the project directory in your terminal.
3. Run `node bug.js` (for the buggy version) or `node bugSolution.js` (for the corrected version).