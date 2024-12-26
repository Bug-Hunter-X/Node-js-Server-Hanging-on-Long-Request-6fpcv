# Node.js Server Hanging on Long Request

This repository demonstrates a common issue in Node.js applications where a long-running operation in a request handler blocks the event loop, causing the server to hang and become unresponsive to new requests.

The `server.js` file contains a simple HTTP server that simulates a long-running task within the request handler. This task blocks the event loop for 5 seconds, preventing the server from handling any other requests during that time.

The `serverSolution.js` file demonstrates a solution using asynchronous operations to prevent blocking the event loop and keep the server responsive.

## How to reproduce the bug

1. Clone this repository.
2. Navigate to the repository directory.
3. Run `node server.js` to start the server.
4. Open multiple browser tabs and try to access the server (e.g., `http://localhost:3000`). You will observe that only the first request is processed immediately, while subsequent requests will only be handled after the first request completes.

## Solution

The solution involves using asynchronous operations to avoid blocking the event loop. This can be achieved using techniques like callbacks, promises, or async/await. The `serverSolution.js` file provides an example of this approach.