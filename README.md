# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js: server unresponsiveness due to a long-running task blocking the event loop. The `server.js` file contains a simple HTTP server with a request handler that simulates a 5-second delay.  During this delay, the server cannot process any other requests, leading to unresponsiveness. The `serverSolution.js` file presents a solution using asynchronous operations.

## How to Reproduce

1. Clone the repository.
2. Run `node server.js`.
3. Try sending multiple requests to the server (e.g., using `curl`). You'll observe that after the first request, subsequent requests will hang until the first one completes.

## Solution

The solution involves offloading long-running tasks to asynchronous operations using techniques such as `setTimeout`, `setInterval`, promises or worker threads. This prevents blocking the event loop and keeps the server responsive. See `serverSolution.js` for an example.