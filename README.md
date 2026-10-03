# Compliment AI

A clean, minimal app for turning screenshots of conversations into sharper replies.

This repository builds to a static site meant for GitHub Pages.

## What it does right now

- One screenshot in
- Three AI-generated reply options out

The app is scoped to that first version only.

## Stack

- React 19
- Vite
- TypeScript
- Tailwind CSS
- shadcn/ui
- Convex for backend and auth
- Framer Motion

## Project setup

```bash
bun install
```

## Development

```bash
bun run dev
```

## Production build for GitHub Pages

```bash
bun run build
```

The built site is output to `dist/`. Deploy that folder to GitHub Pages.

If the site is hosted at a subpath such as `https://<owner>.github.io/<repo>/`, the build is already configured for that. If it is hosted at the root of a custom domain, set the Vite base path to `/` before building.

## Required environment variables

The app still uses Convex. That means the Vite client needs to know the Convex deployment URL at build time.

Set these in GitHub repository settings under **Settings → Secrets and variables → Actions**, or in your local `.env` before building:

```
VITE_CONVEX_URL=<your convex deployment url>
```

The backend also needs an AI provider key to generate reply options. That key belongs on the backend, not in the client bundle.

## GitHub Pages deployment

1. Push the repository to GitHub.
2. Go to **Settings → Pages**.
3. Choose the branch and folder that contains the built site.
4. If you are deploying the `dist` folder directly, make sure the deployment source points to it.

If you want an automated workflow later, add a GitHub Actions job that runs:
```bash
bun install
bun run build
```
and then uploads the `dist` folder to Pages.

## Notes for this version

- The main screen leads with a screenshot upload box.
- After sign-in, the dashboard is the primary experience.
- Auth already redirects signed-in users to `/dashboard` by default.

## Theme

The visual direction is modern, quiet, and premium:

- Crisp typography
- Neutral backgrounds
- One refined accent
- Soft layered cards
- Balanced spacing

No loud gradients or decorative noise.
