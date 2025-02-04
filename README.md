# Unhandled 'error' event in Node.js HTTP server

This repository demonstrates an example of the common 'Unhandled 'error' event' in Node.js and how to solve it.  The bug occurs because an error event is emitted by the HTTP server and it isn't handled.  This typically leads to the server crashing and exiting unexpectedly.

## How to reproduce the bug
1. Clone this repository.
2. Navigate to the directory.
3. Run `node bug.js`.
4. Observe the error message, indicating the unhandled 'error' event. This may be a SIGPIPE error.

## How to solve the bug
The solution involves adding an event listener to the server to handle potential errors gracefully. This prevents the unhandled exception and ensures that the server doesn't crash unexpectedly. The solution code is shown in `bugSolution.js`.  By adding an error handler, the server will continue running even if an error occurs, offering a more robust application.