# React setInterval Cleanup Issue

This repository demonstrates a common React bug: using `setInterval` within the `useEffect` hook without proper cleanup. This can cause memory leaks and unexpected behavior.

## Bug Description

The `MyComponent` component uses `setInterval` to update a counter every second. However, it fails to include a cleanup function in the `useEffect` hook.  This means that when the component unmounts, the interval continues to run, leading to a memory leak.  The counter will continue to increment even after the component is no longer rendered. 

## Solution

The solution involves adding a cleanup function to the `useEffect` hook that uses `clearInterval` to stop the interval when the component unmounts.