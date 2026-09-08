# invoice-test

Take-home assignment: a small admin panel with authentication, a buyers registry and terminal management.

## Features

- **Auth** — a GitHub account is the login: the user is verified with a request to `api.github.com`, which also provides the avatar. The session is kept in `localStorage`, and every internal page sits behind `PrivateRoute`, redirecting to `/login`.
- **Buyers** (`/buyers`) — a table over the mock data in [`src/data/buyers.js`](./src/data/buyers.js) plus a filter form; clicking a row opens a single buyer page (`/buyers/:buyerId`).
- **Terminals** (`/terminals`) — a form to add records and a delete action, with the list persisted to `localStorage`.
- Sidebar, Home, Logout and 404 pages, responsive SCSS layout.

## Stack

React 16, React Router 5, Formik + Yup for forms and validation, SCSS. The project started on Create React App and was later migrated to Vite 5.

## Running

```bash
npm install
npm run dev      # dev server
npm run build    # production build into dist/
npm start        # preview the built version
```
