# Next.js 15 App Router Conflict

This repository demonstrates an unexpected behavior in Next.js 15's App Router when both `pages/index.js` and `app/page.js` exist.  The App Router appears to ignore the file in the `pages` directory. This is unexpected behavior as there are no documentation about this behavior.

## Expected Behavior

It's expected that the App Router would prioritize the `app/page.js` file when both files exist and not load the pages directory file.

## Actual Behavior

The `pages/index.js` file is rendered, overriding the expected behavior of the App Router. The file in the `app` directory is completely ignored.

## Steps to Reproduce

1. Create a Next.js 15 app.
2. Create `pages/index.js` with simple JSX content.
3. Create `app/page.js` with different JSX content.
4. Run the application.
5. Observe that the content of `pages/index.js` is rendered instead of `app/page.js`.

## Solution

Remove the `pages/index.js` file or create a different route in `app` directory.  The App Router should only be used for the app directory.