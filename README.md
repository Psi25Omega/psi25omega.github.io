# arjun-arunachalam.github.io

A minimal Jekyll blog/site: dark theme, small-caps title, colored
blockquotes, LaTeX support via MathJax — styled after a screenshot you
already liked. Home page lists posts; there's an About page; everything
else is just Markdown files.

## What's here

```
_config.yml          site settings — title, description, url
_posts/               blog posts (one file per post)
about.md               the /about/ page
index.html             home page (lists posts automatically)
_layouts/               default.html (page shell), post.html (blog post shell)
_includes/              header.html, footer.html, mathjax.html
assets/css/             _style.scss (all styling), main.css (entry point)
.github/workflows/      GitHub Actions workflow that builds + deploys on push
```

## 1. Create the repo

- If this is your user/organization site, name the repo exactly
  `<your-username>.github.io`, and the site will publish at
  `https://<your-username>.github.io/`.
- If it's a project site, name it anything, and it'll publish at
  `https://<your-username>.github.io/<repo-name>/` — in that case set
  `baseurl: "/<repo-name>"` in `_config.yml`.

On github.com: **New repository** → name it → create it (no need to
initialize with a README, you already have one).

## 2. Push this folder

```bash
cd site   # this folder
git init
git add -A
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

## 3. Turn on Pages

In the repo: **Settings → Pages → Build and deployment → Source** →
select **GitHub Actions**. The included workflow
(`.github/workflows/pages.yml`) will build and deploy automatically on
every push to `main`. First deploy takes a minute or two; check the
**Actions** tab for progress and the live URL.

## 4. Personalize it

- `_config.yml` — set `title`, `description`, `url`, `github_username`.
- `about.md` — replace the placeholder text with a real bio.
- Delete `_posts/2026-07-24-hello-world.md` once you don't need the example.

## Writing a new post

Add a file to `_posts/` named `YYYY-MM-DD-a-short-title.md`:

```markdown
---
title: "My Post Title"
tags: [optional, tags]
math: true   # only needed if the post uses LaTeX
---

Post content in Markdown here. Inline math: $E = mc^2$.
Display math:

$$
\int_0^1 x^2 \, dx = \frac{1}{3}
$$
```

Push to `main` and it appears on the home page automatically, newest
first.

## Local preview (optional)

Needs Ruby + Bundler.

```bash
bundle install
bundle exec jekyll serve
# open http://localhost:4000
```

## Styling

All colors and layout live in `assets/css/_style.scss` as CSS variables
at the top (`--bg`, `--text`, `--accent-green`, `--accent-teal`, etc.) —
edit those to retheme without hunting through the rest of the file.
