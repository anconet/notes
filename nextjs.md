# Notest On Next Js
---
## Tutorial
---
Based on the [NextJs Tutorial](https://nextjs.org/learn/dashboard-app)

### Styling

Using `@` at the begining of an import references the rest of the file to root project directory. (I don't know how Next Js knows nessarily where the root of the project is.)
```javascript
import '@/app/ui/global.css'
```
`import` the `global.css` into the toplevel '@/app/layout.tsx' for the project. This apply the global css to everything.

(todo) Checkout `clsx` library for condisional formatting with `tailwind`.

### Fonts
They add the font to the project to keep the client from having to fetch it. Kind of cool.

Next comes with a bunch of google fonts. They are found it `next/fonts`

### Pages
`Layout.tsx` is a special file name that creates a layout for the Page.tsx file and pages below it.

`Page.tsx` is a special file that is the page that the given route.

`/app` is the home directory.

`/app/Layout.tsx` is the master layout for the website.

`/app/Page.tsx` is the page at `/`

### Navigating between pages
Next Js provides a `<Link>` component to replace `<a>`. It prefetches the server side rendered page that the link connects. So it's super fast.

Example using clsx to conditionally format a component based on a variable
```javascript
          <Link
            key={link.name}
            href={link.href}
            className={
                clsx( 'flex h-[48px] grow items-center justify-center gap-2 rounded-md bg-gray-50 p-3 text-sm font-medium hover:bg-sky-100 hover:text-blue-600 md:flex-none md:justify-start md:p-2 md:px-3',
              {
                'bg-sky-100 text-blue-600': pathname === link.href
              })
            }
          >
```
### Fetching
 
 Pull three queries in parallel with Promise.all

 ```javascript
 export async function fetchCardData() {
  try {
    const invoiceCountPromise = sql`SELECT COUNT(*) FROM invoices`;
    const customerCountPromise = sql`SELECT COUNT(*) FROM customers`;
    const invoiceStatusPromise = sql`SELECT
         SUM(CASE WHEN status = 'paid' THEN amount ELSE 0 END) AS "paid",
         SUM(CASE WHEN status = 'pending' THEN amount ELSE 0 END) AS "pending"
         FROM invoices`;
 
    const data = await Promise.all([
      invoiceCountPromise,
      customerCountPromise,
      invoiceStatusPromise,
    ]);
    // ...
  }
}
```
### Rendering Static and Dynamic

Static data can be rendered faster because it is cached by default on the server. `NextJs` does this by default.

But some dynamic data can't be cached:

Turn off caching using `unstable_noStore` from `next/cache`

```javascript
// ...
import { unstable_noStore as noStore } from 'next/cache';
 
export async function fetchRevenue() {
  // Add noStore() here to prevent the response from being cached.
  // This is equivalent to in fetch(..., {cache: 'no-store'}).
  noStore();
 
  // ...
}
```

### Streaming
Creat a loading page is one option:
`app/loading.tsx` loading.tsx is another magic `NextJs` filename. It leverages `React` `<suspense>` component
```javascript
export default function Loading() {
  return <div>Loading...</div>;
}
```


