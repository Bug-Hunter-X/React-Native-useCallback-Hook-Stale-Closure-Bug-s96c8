# React Native useCallback Hook Stale Closure Bug

This repository demonstrates a common error when using the `useCallback` hook in React Native: stale closures.  The example shows how a function within `useCallback` may not update correctly if its dependencies are not properly specified, leading to unexpected behavior.

## Problem

The `useCallback` hook is intended to memoize functions, preventing unnecessary re-renders.  However, if the function depends on values that change (such as state variables), those dependencies must be listed in the `useCallback`'s dependency array.  Failure to do so results in a stale closure: the function continues to use the old value, even after the dependency has changed.

## Solution

The solution is to correctly specify all dependencies in the dependency array of `useCallback`.  In this case, `count` should be added to the array.