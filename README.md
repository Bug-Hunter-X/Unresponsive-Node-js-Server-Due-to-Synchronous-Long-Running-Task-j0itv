# Unresponsive Node.js Server: A Case Study

This repository demonstrates a common issue in Node.js applications: an unresponsive server caused by a long-running synchronous operation within the request handler.  The event loop becomes blocked, resulting in a frozen server that's unable to handle new requests. This example uses a simple `while` loop to simulate a long task, but it could easily be any other CPU-intensive operation.

## Problem

The `bug.js` file contains a Node.js HTTP server that performs a 5-second synchronous operation in the request handler. This causes the server to hang and become unresponsive to new requests while the long task completes.

## Solution

The `bugSolution.js` file provides a solution by using asynchronous operations (specifically `setTimeout`) to prevent blocking the event loop.  This allows the server to remain responsive even during long-running tasks.