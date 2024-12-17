# JavaScript Closure Issue in setTimeout

This repository demonstrates a common error in JavaScript related to closures and the `setTimeout` function within loops. The issue arises because the closure created by the `setTimeout` callback function does not capture the value of `i` at the time of its creation, but rather captures a reference to the variable `i`. This means by the time the `setTimeout` function finally executes, the loop has already completed and `i` will hold its final value of 10.

## Bug

The `bug.js` file contains the buggy code.  Running this code will print 10 ten times to the console, instead of printing the numbers 0 through 9 as one might expect.

## Solution

The `bugSolution.js` file provides a solution.  This fixes the issue by using an Immediately Invoked Function Expression (IIFE) to create a new scope for each iteration of the loop. Each iteration of the loop gets its own independent copy of the variable `i` in its closure.