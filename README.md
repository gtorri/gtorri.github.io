# gtorri.github.io

Personal notebook site, built with [Quarto](https://quarto.org).

## Setup

1. Install Quarto: https://quarto.org/docs/get-started/
2. Clone this into your `gtorri.github.io` repo (or copy these files into it).
3. Preview locally:
   ```
   quarto preview
   ```

## Publish to GitHub Pages

This config outputs to `docs/`. In the repo's GitHub settings, set
**Pages → Source** to `main` branch, `/docs` folder. Then:

```
quarto render
git add docs _quarto.yml *.qmd *.scss *.css posts
git commit -m "Update site"
git push
```

Or use Quarto's built-in publish command (writes directly to a
`gh-pages` branch instead, if you'd rather not commit `docs/` to `main`
— pick one approach and stick with it):

```
quarto publish gh-pages
```

## Structure

- `index.qmd` — home page
- `notebook.qmd` — auto-generated post listing (pulls from `posts/`)
- `posts/` — one folder per post, each with an `index.qmd`
- `code.qmd`, `talks.qmd`, `now.qmd` — static pages, edit directly
- `styles.scss` / `styles.css` — theme tweaks on top of Bootswatch flatly/darkly

## Adding a post

```
mkdir posts/YYYY-MM-DD-slug
```

Create `index.qmd` inside with a `title`, `date`, and `categories` in the
YAML header (see `posts/2026-01-01-welcome/index.qmd` for an example).
