# `loading.js` in Next.js

## Overview

The `loading.js` file in Next.js is a **special convention** used to define a loading UI for a specific route or layout. It is part of the **App Router** and enables developers to display a loading state while waiting for content to load, such as server-side data fetching or component rendering.

---

![example](./assets/loading-ui.avif)

## Usage

### 1. **Creating a `loading.js` File**

- Place a `loading.js` file in the same directory as your `page.js` or `layout.js` file.
- Example directory structure:

  ***

  ## ![example](./assets/loading-special-file.avif)

### 2. **Basic Example**

```jsx
export default function Loading() {
  return <div>Loading...</div>;
}
```

---

## Where It Is Used

1. **For Pages**:

   - Automatically used when the `page.js` file takes time to load, e.g., during data fetching (`getServerSideProps`, `getStaticProps`, or fetching inside a Server Component).

2. **For Layouts**:
   - Applies to **all child routes** within a layout while they are loading.
   - Example:
     ```plaintext
     /app
       layout.js     → Parent layout
       loading.js    → Shown while any child page is loading
       /profile
         page.js     → Profile page
         loading.js  → Overrides parent `loading.js` for this route
     ```

---

## Key Features

| Feature                    | Description                                                   |
| -------------------------- | ------------------------------------------------------------- |
| **Granular Control**       | Define `loading.js` per route or layout.                      |
| **Automatic Display**      | Shown automatically during fetch or render delays.            |
| **Parent-Child Hierarchy** | A child `loading.js` overrides the parent’s loading behavior. |

---

## Example with Layout

```jsx
// app/dashboard/loading.js
export default function Loading() {
  return (
    <div>
      <p>Loading your dashboard...</p>
      <img src="/spinner.gif" alt="Loading spinner" />
    </div>
  );
}
```

---

## Benefits

- Enhances **user experience** by providing immediate visual feedback.
- Eliminates the feeling of unresponsive pages during **data fetching** or **heavy computation**.
- **Customizable**: Design your own spinners, animations, or placeholders.

---

For more details, visit the [Next.js Loading UI Documentation](https://nextjs.org/docs/app/building-your-application/loading-ui).
