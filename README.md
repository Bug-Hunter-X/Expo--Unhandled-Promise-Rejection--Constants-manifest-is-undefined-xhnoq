# Expo: Unhandled Promise Rejection: Constants.manifest is undefined

This repository demonstrates a common error in Expo projects where `Constants.manifest` is undefined in a native module during early initialization.  This typically occurs because the native module attempts to access the manifest before it's fully loaded by the Expo runtime.

## Bug Description
The issue arises when a native module, often written in JavaScript (using Expo's managed workflow), attempts to access properties of `Constants.manifest` before the Expo client has fully initialized these values. This leads to an `undefined` error during runtime.

## Solution
The solution involves delaying access to `Constants.manifest` until it's guaranteed to be populated.  This is achieved using an asynchronous approach (like promises or async/await) that ensures the module waits for the Expo client to finish initialization before trying to use the manifest data.

## How to Reproduce
1. Clone the repository.
2. Install the project dependencies: `npm install` or `yarn install`.
3. Run the app: `expo start`
4. Observe the error in the console.