# Introduction to Next.js

Next.js is a powerful **React framework** developed by Vercel that allows developers to create server-rendered and statically generated web applications. It simplifies development by offering features like server-side rendering (SSR), static site generation (SSG), and hybrid capabilities out of the box. With **Next.js 14**, it introduces improvements in:

1. **Performance**: Enhanced optimizations for both client-side and server-side rendering.
2. **Server Actions**: Native support for server-side business logic.
3. **Routing**: An upgraded app router with improved layouts and loading states.
4. **Streaming & Edge Rendering**: Faster and more dynamic updates using server-side streaming.
5. **Built-in AI Integration**: Simplifies building AI-powered features.

---

### Installation of Next.js 14

To get started with Next.js 14, follow these steps:

1. **Initialize a New Project**:

   ```bash
   npx create-next-app@latest my-next-app
   ```

   This command sets up the project with TypeScript, ESLint, Tailwind CSS, and other features by default. You can customize the options during the setup process.

2. **Navigate to the Project Directory**:

   ```bash
   cd my-next-app
   ```

3. **Run the Development Server**:

   ```bash
   npm run dev
   ```

   This starts the development server at `http://localhost:3000`.

4. **Upgrade to Next.js 14** (if you're using an older version):
   ```bash
   npm install next@latest react@latest react-dom@latest
   ```

---

### Key Files and Features in Next.js 14

#### 1. **`page.js`**

- Located inside the `/app` directory, `page.js` files are responsible for defining routes in the application. For example:
  ```plaintext
  /app/about/page.js → /about
  /app/contact/page.js → /contact
  ```
- A simple `page.js` file example:
  ```jsx
  export default function Page() {
    return <h1>Welcome to About Page</h1>;
  }
  ```
- Each `page.js` is automatically treated as a React Server Component (RSC), allowing you to fetch data and render content server-side.

---

#### 2. **`layout.js`**

- **Purpose**: Defines layouts for a route or group of routes.
- **Structure**: A `layout.js` file wraps the UI for a set of pages under a specific route.
- Example:
  ```jsx
  export default function Layout({ children }) {
    return (
      <div>
        <header>Header Section</header>
        <main>{children}</main>
        <footer>Footer Section</footer>
      </div>
    );
  }
  ```
- **Nesting Layouts**:
  Layouts can be nested to create unique layouts for different sections of the app:
  ```plaintext
  /app
    layout.js      → Base layout
    /dashboard
      layout.js    → Dashboard-specific layout
      page.js      → Dashboard page
  ```

---

#### 3. **App Routing**

- **File System Routing**:
  Routes are determined by the structure of the `/app` directory. Each folder becomes a route, and `page.js` files define the content for those routes.
- **Dynamic Routes**:
  Dynamic routes are created using brackets in folder names. Example:

  ```plaintext
  /app/products/[id]/page.js → /products/:id
  ```

  Dynamic routing in `page.js`:

  ```jsx
  export default function ProductPage({ params }) {
    return <h1>Product ID: {params.id}</h1>;
  }
  ```

- **Special Files**:

  - `error.js`: Renders a fallback UI in case of errors.
  - `loading.js`: Shows a loading state while the route or data is loading.
  - `not-found.js`: Customizes the 404 page for the route.

- **Middleware**: Define custom logic for routes in the `middleware.js` file located in the root.

---

### Example Directory Structure

![example](./assets/terminology-component-tree.avif)

### Conclusion

Next.js 14 makes it easier than ever to create performant, scalable, and modern web applications. With its file-based routing system, built-in layouts, and server-first approach, it simplifies both the developer and user experience.
