# yoursimpleguide.com

Personal reference site built with Quarto, hosted on GitHub Pages.

## Everyday workflow

```bash
quarto preview          # live preview while you edit, updates as you save
quarto render           # build the site into docs/
git add .
git commit -m "Post week of Aug 17"
git push
```

The live site updates about a minute after you push.

## Posting a new weekly assignment

Edit `homeschool/weekly.qmd`. Move the current week down into the "Past weeks"
section as a collapsed callout, then write the new week at the top. Render,
commit, push.

## Adding a new topic section

1. Create a folder, for example `recipes/`, with an `index.qmd` inside.
2. Add the page to the `navbar` list in `_quarto.yml`.
3. Render, commit, push.

## Important files

- `_quarto.yml` — site config, menu, output folder
- `styles.scss` — colors and fonts
- `CNAME` — holds the custom domain, gets copied into `docs/` on every render
- `.nojekyll` — tells GitHub Pages not to run Jekyll on the output

Do not delete `CNAME` or `.nojekyll`. If the site suddenly loses its styling or
the domain stops working, check that both files exist inside `docs/` after a
render.

## First time setup

### 1. Install

- Quarto: https://quarto.org/docs/get-started/
- Git: https://git-scm.com/downloads
- A GitHub account: https://github.com

### 2. Push to GitHub

Create an empty repo on GitHub named `yoursimpleguide` (public, no README).
Then in this folder:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOURUSERNAME/yoursimpleguide.git
git push -u origin main
```

### 3. Turn on GitHub Pages

Repo → Settings → Pages → Build and deployment → Deploy from a branch →
branch `main`, folder `/docs` → Save.

### 4. Point the domain (Hostinger)

In Hostinger: Domains → yoursimpleguide.com → DNS / Nameservers.

Delete any existing A record on `@` and any CNAME on `www`, then add:

| Type | Name | Points to |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | YOURUSERNAME.github.io |

Then back in GitHub → Settings → Pages → Custom domain, enter
`yoursimpleguide.com` and save. Once the check passes, tick **Enforce HTTPS**.
