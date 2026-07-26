# prophetic.technology

Personal site for Steph Alinsug. Static HTML, no framework, no build step.

## Deploy pipeline — read this before committing

```
push to main  →  GitHub  →  Vercel builds  →  live at prophetic.technology (~20s)
```

**A push to `main` is a production deploy to a public domain.** There is no staging
gate. Treat every commit to `main` as publishing.

Pushes to any other branch produce a private Vercel preview URL instead. For anything
substantial or visually uncertain, work on a branch and let the preview be the check.

Vercel is already connected to this repo. Nothing about deployment needs configuring,
and there is no CI to satisfy.

## Stack

Plain HTML and CSS. Styles live inline in a `<style>` block in each page.

Do not add a framework, bundler, package manager, or CSS preprocessor without being
asked. If a task seems to call for one, say so and wait for a decision. `package.json`
appearing in this repo would change how Vercel builds the site.

## Structure

File paths map directly to URLs:

| File | URL |
|---|---|
| `index.html` | `/` |
| `about.html` | `/about` |
| `notes/index.html` | `/notes` |

## Conventions

- Semantic HTML. Real `<h1>`/`<nav>`/`<main>`, not `<div>` soup.
- Every page carries `<meta name="viewport">`, a unique `<title>`, and a
  `<meta name="description">`.
- Colors come from the CSS custom properties defined in `index.html`
  (`--ink`, `--paper`, `--muted`, `--rule`). Reuse them; don't hardcode hex values.
- Dark mode via `prefers-color-scheme` is supported and should stay supported on
  new pages.
- Mobile-first. Check narrow widths before shipping.
- No analytics, trackers, or third-party scripts unless explicitly requested.

## Local preview

```bash
python3 -m http.server 8000   # → http://localhost:8000
```

## Committing

Commit messages: imperative, lowercase, specific. `add notes index`, not
`Update files`.

Ask before pushing to `main`. Never force-push, never rewrite published history.
