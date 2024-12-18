# Express.js - req.body undefined despite using express.json()

This repository demonstrates a common issue in Express.js applications where `req.body` remains undefined even after using the `express.json()` middleware to parse JSON request bodies.  The issue arises from improper middleware placement or configuration.  This repository contains both the buggy code and its corrected version.  See `bug.js` for the flawed implementation and `bugSolution.js` for the solution.

## Bug Description

The original code attempts to create a simple POST endpoint that expects a JSON payload.  However, due to the bug in middleware placement, `req.body` remains undefined, preventing access to the request body data.

## Solution

The corrected code ensures that the `express.json()` middleware is placed before the route handler that attempts to access `req.body`.  This correct order ensures that the middleware has the opportunity to parse the JSON body before the route handler executes.

## Setup

1. Clone the repository
2. Run `npm install` to install express
3. Run `node bug.js` to run the buggy version (you'll see an error in the console)
4. Run `node bugSolution.js` to run the corrected version