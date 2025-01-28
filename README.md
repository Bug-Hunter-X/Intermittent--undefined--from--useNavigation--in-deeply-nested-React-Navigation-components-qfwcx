# React Navigation useNavigation() Intermittency Bug

This repository demonstrates a subtle bug in React Navigation where the `useNavigation()` hook inconsistently returns `undefined` when used within deeply nested functional components.  The issue is exacerbated when using context providers or state management solutions.

## Problem Description

The `useNavigation()` hook, used for navigation within React Navigation, returns `undefined` under specific, hard-to-replicate conditions. This generally occurs within components nested several levels deep inside the main navigation structure.  No obvious error messages are logged, making debugging challenging.

## Solution

The solution involves ensuring the navigation context is properly propagated and available to the deeply nested component.  This can be achieved in a number of ways, such as using a dedicated Context provider to explicitly pass the navigation object down, or by carefully restructuring the component tree to reduce the nesting depth.  The provided solution demonstrates the Context-based approach.

## How to reproduce

1. Clone this repository.
2. Run `npm install`
3. Run `npx react-native run-android` or `npx react-native run-ios`
4. Observe the intermittent behavior of the `DeeplyNestedScreen` component. 