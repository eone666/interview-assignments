# Interview assignments

A collection of front-end take-home assignments: the original brief from each company plus my implementation.

Every folder is a standalone project with its own `package.json` and its own README that keeps the original task text. Projects are listed in chronological order, earliest first.

| Project | Assignment | Stack | Run |
| --- | --- | --- | --- |
| [`invoice-test`](./invoice-test) | Admin panel: auth, buyers, terminals | React 16, React Router 5, Formik + Yup, SCSS, Vite | `npm i && npm run dev` |
| [`rating-test`](./rating-test) | Construction-site report registry + 3-step form | React 16, CRA, Bootstrap 4, Formik + Yup, moment | `yarn && yarn start` |
| [`welcome_to_TE`](./welcome_to_TE) | 5 exercises on reactivity and render optimization | React (standalone files, no build) | — |
| [`alinakz-test`](./alinakz-test) | Request-management SPA: dashboard, form, tables | React 18, TypeScript, Redux Toolkit + saga, Tailwind, Radix UI, Recharts, Vite | `npm i && npm run dev` |
| [`raison-test`](./raison-test) | Responsive layout from a mockup + two-step login flow | HTML/CSS, React 18, TypeScript, Tailwind, Vite | see the [readme](./raison-test/readme.md) |

Requirements: Node.js 18+ and npm (`rating-test` uses yarn).

> The original briefs inside `rating-test`, `welcome_to_TE`, `alinakz-test` and `raison-test` are in Russian — they are kept verbatim as the companies wrote them.

---

## invoice-test

A small admin panel behind private routes.

- **Auth** — a GitHub account is the login: the user is verified with a request to `api.github.com`, which also provides the avatar; the session is kept in `localStorage`.
- **Buyers** — a table over mock data, a filter form, and a page for a single buyer.
- **Terminals** — adding and deleting records, persisted to `localStorage`.
- Home, Logout and 404 pages, a sidebar, responsive SCSS layout.

Forms are built with Formik and Yup schemas. The project started on Create React App and was later migrated to Vite.

```bash
cd invoice-test
npm install
npm run dev      # dev server
npm run build    # production build into dist/
npm start        # preview the built version
```

## rating-test

The [rating.kz](./rating-test/README.md) assignment: a registry of reports for a construction site and a form to add one.

- a site filter and a report table (name, description, date, status, whether there are remarks);
- a 3-step add form, each step full-page, with a progress indicator;
- step 2 holds a nested registry of remarks, step 3 is confirmation plus the list of validation errors;
- layout on Bootstrap 4 via `react-bootstrap`, validation with Formik + Yup.

```bash
cd rating-test
yarn install
yarn start       # dev server on :3000
yarn build       # production build
```

> Dictionaries and saving go through the API from the brief (`http://178.90.223.230:6132`). That is the company's own test environment — if it is unreachable, the lists stay empty.

## welcome_to_TE

The [TileExpert](./welcome_to_TE/README.md) assignment — five independent exercises on how React renders. There is no application here: each folder holds a `README.md` with the problem and an `index.{jsx,tsx}` with the solution.

| Task | Problem | Solution |
| --- | --- | --- |
| [task_1](./welcome_to_TE/task_1) | re-renders even when `props` do not change | `memo`, `PureComponent`, `shouldComponentUpdate` |
| [task_2](./welcome_to_TE/task_2) | memoization broken by a new callback on every render | `useCallback` |
| [task_3](./welcome_to_TE/task_3) | memoization broken by a default object in `props` | a constant outside the component + a custom comparator in `memo` |
| [task_4](./welcome_to_TE/task_4) | a class component controlled through a `ref` has to become functional | `forwardRef` |
| [task_5](./welcome_to_TE/task_5) | five components sharing the same logic and markup | one wrapper component, differences passed as `children` |

## alinakz-test

A request-management SPA built from a [reference design](https://www.figma.com/file/XmDhPyJ8GaYRqTNcIrRptJ/Test) — the full brief is in the [project README](./alinakz-test/README.md).

- **Dashboard** — four Recharts diagrams: a monthly currency-rate line chart, KPI completion, a bar chart of requests by status, and a horizontal bar chart;
- **New request** — a `react-hook-form` + `zod` form with every field type from the brief (text, number, money, masked phone, select, calendar, checkbox, radio group); the "Clear" button unlocks as soon as one field is filled, and the submit result is shown in a toast;
- **My / accepted / rejected requests** — a 10-column table, pagination (100 pages of 20 records), delete with confirmation, pulling a record up from the next page and renumbering the rows;
- state in Redux Toolkit, side effects in redux-saga, requests via axios, UI in Tailwind on top of Radix primitives, icons imported as components through `vite-plugin-svgr`;
- responsive layout; the sidebar collapses on small screens.

The mock API is `json-server` over [`data/db.json`](./alinakz-test/data/db.json), with the base URL taken from an environment variable.

```bash
cd alinakz-test
cp .env.sample .env       # VITE_API_BASEURL, defaults to http://localhost:3000/
npm install
npm run dev               # client (vite) and mock API (json-server) in one command
npm run build
npm run lint
```

## raison-test

Two assignments in one repository — see the [shared description](./raison-test/readme.md).

### [test-1-html+css](./raison-test/test-1-html+css)

A responsive page built from a [mockup](https://www.figma.com/file/xWtuy7DRC8UmveMbkcC9PU/Developer-Testing) in plain HTML and CSS, no frameworks: a hand-written reset, SVG graphics (map, flags), and support not only for the desktop and mobile widths in the mockup but for the range in between.

```bash
cd raison-test/test-1-html+css
npm install
npm run dev
```

### [test-2-react](./raison-test/test-2-react)

A two-step login flow on React Router: email validation with the value kept in `sessionStorage`, a "Hold to proceed" button with a 500 ms hold and a timer that counts back down if released early, a `POST` to `api/endpoint` on the second step, and a result popup that closes with the hardware Back button.

```bash
cd raison-test/test-2-react
npm install
npm run dev      # client (vite) and express mock server (:4040) in one command
```

Requests to `/api/*` are proxied to the mock server — see [`vite.config.ts`](./raison-test/test-2-react/vite.config.ts) and [`server.js`](./raison-test/test-2-react/server.js).
