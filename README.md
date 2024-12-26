# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js applications: blocking the event loop with a long-running synchronous operation.  This leads to the server becoming unresponsive and unable to handle new requests.

## Problem
The `blocking_server.js` file contains a Node.js HTTP server that performs a 5-second synchronous operation within the request handler. During this time, the event loop is blocked, preventing the server from responding to other requests.

## Solution
The `non_blocking_server.js` file shows how to resolve the issue by using asynchronous operations or offloading the long-running task to a worker thread or a separate process. This prevents blocking the main event loop and ensures the server remains responsive.

## How to Run

1. Clone this repository
2. Navigate to the repository's directory
3. Run `node blocking_server.js` to see the blocking behavior.  Try sending multiple requests to the server.  You'll observe that the server will not respond until the 5-second loop completes.
4. Run `node non_blocking_server.js` to see the improved responsive behavior.  Try sending multiple requests; the server should handle them concurrently.