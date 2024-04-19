## Next.js App Router Course - Starter

This is the starter template for the Next.js App Router Course. It contains the starting code for the dashboard application.

For more information, see the [course curriculum](https://nextjs.org/learn) on the Next.js Website.

# App Structure

- `/app`: Contains all the routes, components, and logic for your application, this is where you'll be mostly working from.
- `/app/lib`: Contains functions used in your application, such as reusable utility functions and data fetching functions.
- `/app/ui`: Contains all the UI components for your application, such as cards, tables, and forms. To save time, we've pre-styled these components for you.
- `/public`: Contains all the static assets for your application, such as images.
- `/scripts`: Contains a seeding script that you'll use to populate your database in a later chapter.
- `Config Files`: You'll also notice config files such as next.config.js at the root of your application. Most of these files are created and pre-configured when you start a new project using create-next-app. You will not need to modify them in this course.

# Postgres SDK

```bash
npm i @vercel/postgres
```

# Optimising

To recap, you've done a few things to optimize data fetching in your application, you've:

- Created a database in the same region as your application code to reduce latency between your server and database.
- Fetched data on the server with React Server Components. This allows you to keep expensive data fetches and logic on the server, reduces the client-side JavaScript bundle, and prevents your database secrets from being exposed to the client.
- Used SQL to only fetch the data you needed, reducing the amount of data transferred for each request and the amount of JavaScript needed to transform the data in-memory.
- Parallelize data fetching with JavaScript - where it made sense to do so.
- Implemented Streaming to prevent slow data requests from blocking your whole page, and to allow the user to start interacting with the UI without waiting for everything to load.
- Move data fetching down to the components that need it, thus isolating which parts of your routes should be dynamic in preparation for Partial Prerendering.

# Search methods & Hooks

These are the Next.js client hooks that you'll use to implement the search functionality:

- useSearchParams- Allows you to access the parameters of the current URL. For example, the search params for this URL `/dashboard/invoices?page=1&query=pending` would look like this: {page: '1', query: 'pending'}.
- usePathname - Lets you read the current URL's pathname. For example, for the route `/dashboard/invoices`, usePathname would return '`/dashboard/invoices`'.
- useRouter - Enables navigation between routes within client components programmatically. There are multiple methods you can use.
