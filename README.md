# React Native Dimensions API Returns Undefined on Android

This repository demonstrates a common issue encountered when using the `Dimensions` API in React Native on Android. The problem arises when attempting to access screen dimensions before they are fully available, resulting in `undefined` values.

## Problem

The `Dimensions.get('window')` or `Dimensions.get('screen')` methods might return `undefined` during the initial render of a component.  This is because the dimensions aren't immediately available when the component mounts.  If your component relies on these values for layout or calculations without handling this potential `undefined` value, it will likely result in errors.

## Solution

The solution involves checking if the dimensions are available before using them.  This can be accomplished using a combination of `useEffect` and state management to ensure the dimensions are fetched asynchronously and are available before usage.