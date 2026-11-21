# alistairheys.com

Personal site built with Jekyll, hosted free on GitHub Pages.

## Structure

```
index.html            Homepage (who I am, what I do, experience, latest posts, contact)
blog/index.html       List of all posts
_posts/               One Markdown file per blog post
_layouts/             Page templates (default, post)
_includes/            Header, footer, post list
assets/css/style.css  All styling (light + dark mode)
_config.yml           Site settings: title, email, LinkedIn URL
CNAME                 Custom domain
```

## First-time setup

1. Create a public GitHub repo, e.g. `alistairheys.com` (any name works).
2. Upload everything in this folder to the repo's `main` branch.
3. In the repo: **Settings > Pages**. Under "Build and deployment", set Source to **Deploy from a branch**, branch `main`, folder `/ (root)`.
4. Still on that page, enter `alistairheys.com` as the custom domain.
5. At your domain registrar, add these DNS records:
   - Four `A` records for `@` pointing to:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - One `CNAME` record for `www` pointing to `YOUR-GITHUB-USERNAME.github.io`
6. Once DNS resolves (minutes to a few hours), tick **Enforce HTTPS** in Settings > Pages.

Tip: verify the domain under your GitHub account (**Settings > Pages > Add a domain**) so nobody else can claim it.

## Before going live

Edit `_config.yml`:
- `email` (currently a placeholder)
- `linkedin` (replace `YOUR-HANDLE`)

Optionally add dates to the experience list in `index.html`.

## Writing a post

Create a file in `_posts/` named `YYYY-MM-DD-short-title.md`:

```markdown
---
title: "Your post title"
description: "One line that appears under the title and in the post list."
---

Your post in Markdown.
```

Commit it (you can do this right in the GitHub website with "Add file > Create new file").
The post appears at `/blog/YYYY/MM/short-title/` within a couple of minutes, and on the homepage under "Latest writing".

Images: put them in `assets/img/` and reference them as `![Alt text](/assets/img/name.png)`.

## Previewing locally (optional)

```
bundle install
bundle exec jekyll serve
```
Then open http://localhost:4000.
