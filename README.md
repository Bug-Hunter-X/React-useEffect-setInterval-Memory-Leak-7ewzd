# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications involving the `useEffect` hook and `setInterval`.  The example shows a memory leak caused by neglecting to clear the interval when the component unmounts.

## Bug Description
The `MyComponent` uses `setInterval` to update a counter every second. However, it fails to include a cleanup function within the `useEffect` hook to clear the interval using `clearInterval` when the component unmounts. This leads to a memory leak because the interval continues to run even after the component is removed from the DOM. 

## Bug Solution
The solution involves adding a cleanup function to the `useEffect` hook to clear the interval using `clearInterval` before the component unmounts.