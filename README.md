# React Router Dom v6 Catch All Route Bug

This repository demonstrates a bug in React Router Dom v6 where the catch-all route (`/*`) doesn't work as expected.  The catch-all route should match any route that isn't explicitly defined, but in this case, it's being ignored.

## Bug Description

The `/*` route is intended to act as a fallback for any unmatched routes, displaying a 404 Not Found page. However, the current implementation fails to do so, leading to unexpected behavior. 

## Solution

The solution involves ensuring that the catch-all route is placed after all other routes within the `<Routes>` component.  This ensures that React Router evaluates other routes first and defaults to the catch-all route only if no other match is found. 

## How to reproduce the bug

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Navigate to any path that does not match `/` or `/about`. You will see that the `NotFound` component is not rendered.