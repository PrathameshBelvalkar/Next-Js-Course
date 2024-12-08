# `<Image>` Component in Next.js

## Overview

The `<Image>` component in Next.js is an optimized replacement for the standard `<img>` tag. It provides built-in support for **image optimization**, **lazy loading**, **responsive resizing**, and **formats like WebP**, ensuring better performance and a smoother user experience.

---

## Features

1. **Automatic Optimization**:

   - Images are served in modern formats (e.g., WebP) where supported.
   - Resized and compressed on the server for optimal delivery.

2. **Lazy Loading**:

   - Images load only when they appear in the viewport, reducing initial load time.

3. **Responsive Support**:

   - Automatically adjusts to different screen sizes and resolutions.

4. **Customizable**:
   - Supports properties like `width`, `height`, and `priority` for precise control.

---

## Basic Usage

```jsx
import Image from "next/image";

export default function Home() {
  return (
    <div>
      <Image src="/example.jpg" alt="Example Image" width={500} height={300} />
    </div>
  );
}
```

---

## Key Properties

| Property      | Description                                                                    |
| ------------- | ------------------------------------------------------------------------------ |
| `src`         | Path or URL to the image file. Supports local and remote URLs.                 |
| `alt`         | Alternative text for accessibility. **Required**.                              |
| `width`       | Fixed width of the image (in pixels).                                          |
| `height`      | Fixed height of the image (in pixels).                                         |
| `fill`        | Makes the image fill its container. Use with `objectFit` and `objectPosition`. |
| `priority`    | Loads the image eagerly, ideal for above-the-fold content.                     |
| `placeholder` | Displays a low-quality preview (`blur`) or empty (`empty`).                    |
| `sizes`       | Defines responsive image sizes for different screen widths.                    |

---

## Advanced Usage

### Responsive Image Example:

```jsx
<Image
  src="/example.jpg"
  alt="Responsive Image"
  width={0}
  height={0}
  sizes="(max-width: 768px) 100vw, 50vw"
  style={{ width: "100%", height: "auto" }}
/>
```

## Benefits

- Reduces **Largest Contentful Paint (LCP)** time for better SEO.
- Minimizes manual image handling.
- Supports modern formats for bandwidth efficiency.
