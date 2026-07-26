# prophetic.technology

Static site deployed to Vercel from this repo.

## How publishing works

Every push to `main` triggers a Vercel production deploy to prophetic.technology.
Every push to any other branch (or any pull request) gets its own preview URL.

## Adding a page

Drop an HTML file in the repo root or a subfolder. The path maps to the URL:

| File | URL |
|---|---|
| `index.html` | `/` |
| `about.html` | `/about` |
| `notes/index.html` | `/notes` |

No build step. No framework. If you later want Next.js, Vercel will detect it
from `package.json` and switch the build automatically.

## Local preview

```bash
python3 -m http.server 8000
# open http://localhost:8000
```
