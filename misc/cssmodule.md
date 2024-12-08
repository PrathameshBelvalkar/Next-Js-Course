# `module.css` in Next.js

## Overview

`module.css` is a way to write **scoped CSS** for components in Next.js. It ensures styles are locally scoped to the specific component, avoiding global conflicts.

---

## Features

1. **Scoped Styles**:
   - CSS classes are automatically scoped to the component where they are imported.
2. **No Naming Conflicts**:
   - Class names are transformed into unique identifiers.
3. **Component-Based Styling**:
   - Keeps styles modular and easier to maintain.
4. **Native CSS**:
   - Write regular CSS without needing a preprocessor.

---

## Basic Usage

1. **Create a CSS Module**:

   - File name must end with `.module.css`, e.g., `button.module.css`:
     ```css
     /* Button.module.css */
     .button {
       background-color: blue;
       color: white;
       padding: 10px;
       border: none;
       border-radius: 5px;
     }
     ```

2. **Import in a Component**:

   ```jsx
   import styles from "./button.module.css";

   export default function Button() {
     return <button className={styles.button}>Click Me</button>;
   }
   ```

3. **Generated Class Name**:
   - Next.js transforms `.button` into a unique class like `Button_button__3fG2A`, ensuring no conflicts.

---

## Benefits

- **Scoped Styles**: Avoids unintended style overrides.
- **Reusable Components**: Encapsulated styles keep components portable.
- **Type Safety**: Works seamlessly with TypeScript for typed styles.
