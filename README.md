# SMIT Multi-Portal Website (Student / Admin / Institution)

Static React website (JSX only, no TypeScript) built with Vite, React Router, and Tailwind CSS.

## Run in development

```
npm install
npm run dev
```

Open the printed local URL (usually http://localhost:5173).

## Build for production

```
npm run build
```

This generates a `dist/` folder with the final static site (already included in this zip,
so you can also just open `dist/index.html` behind a static server / deploy it as-is).

To preview the production build locally:

```
npm run preview
```

## Routes

| URL                     | Page               |
|-------------------------|---------------------|
| `/`                      | Landing — pick a portal + mock login |
| `/student/dashboard`     | Student dashboard |
| `/student/attendance`    | Student attendance |
| `/student/progress`      | Student progress |
| `/student/quiz`          | Student quiz results |
| `/admin/dashboard`       | Admin dashboard |
| `/admin/attendance`      | Admin attendance management |
| `/admin/progress`        | Admin batch progress |
| `/admin/quiz`            | Admin quiz management |
| `/institution/dashboard` | Institution dashboard |
| `/institution/attendance`| Institution attendance analytics |
| `/institution/progress`  | Institution progress analytics |
| `/institution/quiz`      | Institution quiz analytics |

## Project structure

```
smit-portal/
├── dist/                      -> production build (ready to deploy)
├── index.html
├── package.json
├── vite.config.js
├── src/
│   ├── main.jsx                -> React entry point
│   ├── App.jsx                 -> All routes (react-router-dom)
│   ├── index.css                -> Tailwind import
│   ├── data/
│   │   ├── mockData.jsx         -> Mock data for all 3 portals
│   │   └── portals.jsx          -> Portal + nav configuration
│   ├── components/
│   │   ├── FontStyle.jsx
│   │   ├── Card.jsx
│   │   ├── StatCard.jsx
│   │   ├── Bar.jsx
│   │   ├── Ring.jsx
│   │   ├── Badge.jsx
│   │   ├── Sidebar.jsx
│   │   └── Topbar.jsx
│   ├── layouts/
│   │   └── PortalLayout.jsx     -> Sidebar + Topbar + <Outlet/> shell
│   └── pages/
│       ├── Landing.jsx           -> Portal picker + mock login
│       ├── student/{Dashboard,Attendance,Progress,Quiz}.jsx
│       ├── admin/{Dashboard,Attendance,Progress,Quiz}.jsx
│       └── institution/{Dashboard,Attendance,Progress,Quiz}.jsx
```

## Notes

- Fully responsive: sidebar collapses into a mobile drawer under `md` breakpoint.
- Login is a mock (any text works — there's no backend).
- All data lives in `src/data/mockData.jsx` — edit it to change what shows up on each page.
