# Firebase Data Race Condition: Inconsistent Counter Updates

This repository demonstrates a common yet subtle error in Firebase applications involving data race conditions.  The problem occurs when attempting to update data based on a previously read value without proper synchronization.

## Problem Description

The `bug.js` file illustrates an incorrect approach to updating a counter in a user's profile.  Because the read and write operations are separate, another client could modify the data in between, causing inconsistencies. This is a race condition.

## Solution

The `bugSolution.js` file presents a correct approach using Firebase transactions to ensure atomicity and prevent race conditions. Transactions guarantee that the update occurs only if the data hasn't changed since it was last read.