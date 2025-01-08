# React useEffect Infinite Loop Bug

This repository demonstrates a common React bug involving the `useEffect` hook causing an infinite loop. The issue arises from a missing dependency in the `useEffect`'s dependency array. When a component rerenders, the effect runs again, which updates the state, leading to another re-render, and so on.

## Bug Description
The `MyComponent` uses `useState` to track a count and an `useEffect` hook to log this count to the console. The effect function depends implicitly on the `count` variable, but this dependency is not listed in the `useEffect`'s dependency array.  Consequently, whenever the component re-renders (which happens every time the count updates), the effect runs again, causing an infinite loop.

## Solution
The solution involves including `count` as a dependency to the `useEffect` hook's dependency array. This ensures that the effect only runs when the value of `count` changes.