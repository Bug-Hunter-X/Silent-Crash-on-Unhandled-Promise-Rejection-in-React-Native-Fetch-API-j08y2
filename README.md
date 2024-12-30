# Silent Crash on Unhandled Promise Rejection in React Native Fetch API

This repository demonstrates a common, yet elusive bug in React Native applications involving unhandled promise rejections during network requests using the Fetch API. The application crashes silently, without providing any clear error message in the console, making debugging difficult.

## Bug Description
The provided `DataList.js` component fetches data from an external API using `fetch`.  While error handling is included within the `try...catch` block, unhandled promise rejections can still occur if an error happens outside this block, leading to a crash.

## How to Reproduce
1. Clone this repository.
2. Run the app on an Android or iOS emulator/device.
3. Observe that the app might crash without any clear error message in the console.  Note that the behavior might be inconsistent depending on the environment and the API's response.

## Solution
The solution is to add a global error handler to catch any unhandled promise rejections. This can be achieved by adding an `unhandledRejection` event listener, as demonstrated in the `DataListSolution.js` file.

## Technologies Used
* React Native
* Fetch API
* Javascript