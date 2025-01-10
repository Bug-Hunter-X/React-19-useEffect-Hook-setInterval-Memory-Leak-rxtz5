# React 19 useEffect Hook setInterval Memory Leak
This repository demonstrates a common error in React 19 involving the `useEffect` hook and the `setInterval` function.  Improper use of `setInterval` within `useEffect` without a cleanup function leads to memory leaks.  The solution showcases the correct way to handle `setInterval` for preventing memory leaks and ensuring efficient component lifecycle management.

## Bug Description
The bug arises when `setInterval` is used within `useEffect` without proper cleanup.  When the component unmounts, the interval continues running, consuming resources and potentially leading to unexpected behavior.  This is a classic memory leak scenario.

## Solution
The provided solution introduces a cleanup function to the `useEffect` hook. This function clears the interval when the component unmounts, preventing the memory leak.  The key is returning a function from `useEffect` that stops the interval before the component is destroyed.