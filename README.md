# React useEffect Hook Memory Leak with setInterval

This repository demonstrates a common error in React applications involving memory leaks caused by the improper use of the `setInterval` function within the `useEffect` hook.  The example component uses `setInterval` to update a counter, but fails to properly clean up the interval when the component is unmounted, leading to a memory leak.

## Problem

The primary issue is the missing cleanup function in the `useEffect` hook.  Without a cleanup function, the `setInterval` continues to run even after the component is unmounted, resulting in unnecessary updates and potential memory leaks. 

## Solution

The solution involves using a cleanup function within the `useEffect` hook to clear the interval when the component is unmounted.  This ensures that the interval is stopped, preventing further memory consumption and avoiding potential issues.

## How to reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the React development server.
4. Observe the counter in the browser.  The counter will continue to increment even if you navigate away from the page.  This demonstrates the memory leak.
