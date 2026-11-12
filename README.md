# Static Blog Template (Gatsby + Netlify CMS)

A ready-made blog website. You write articles as simple Markdown files, and the project turns them into a fast static website with a home page, article pages, tag pages, pagination, a contact form and a 404 page. It also includes a browser-based editor (Netlify CMS) so articles can be written without touching code.

[Live demo](https://static-blog.netlify.app/)

## What it does

- Builds a blog from Markdown files in `content/blog/`.
- Home page with featured and recent posts, paginated post list, and a page per tag.
- Contact form (works when hosted on Netlify, which collects the submissions).
- Netlify CMS editor at `/admin/` for writing and publishing posts through Git.
- SEO tags, sitemap, `robots.txt` and a web app manifest generated at build time.
- Styled with Tailwind CSS, with Storybook for developing the UI components.

## Tech stack

- Gatsby 2 and React 16, written in TypeScript
- Tailwind CSS 1.x and styled-components
- Markdown content via `gatsby-transformer-remark`
- Netlify CMS (`git-gateway` backend) and Netlify Forms
- Storybook 5 and Jest for components and tests

## Run it locally

You need Node.js (an older LTS such as Node 12 or 14 is the safest choice, because this project uses Gatsby 2 and packages from 2020).

```bash
npm install
npm run dev:css   # in one terminal: builds Tailwind into static/css/index.css and watches for changes
npm run dev:js    # in another terminal: starts the site at http://localhost:8000
```

`npm run dev` starts the site, the CSS watcher and Storybook (port 6006) together.

## Build a static copy (for hosting a demo)

```bash
npm run build     # builds the CSS, then the Gatsby site into public/
npm run serve     # optional: preview the build at http://localhost:9000
```

The `public/` folder is plain static files and needs no secrets or environment variables, so it can be uploaded to any static host (Netlify, GitHub Pages, Vercel and so on). The `build` script uses a Unix-style `NODE_ENV=production` prefix, so on Windows run it from WSL or Git Bash.

Other scripts: `npm run lint`, `npm test`, `npm run build:storybook`, `npm run generate-favicon`.

## Deploy your own copy on Netlify

Netlify can host the site, collect contact form submissions and run the CMS.

1. Use this repository (or the original template) as the source of a new Netlify site. Build command: `npm run build`, publish directory: `public`.
2. In the Netlify dashboard, turn on Identity and Git Gateway so people can log in at `/admin/`.
3. Edit the site name, URL and description at the top of `gatsby-config.js`.

Without Netlify the blog itself works, but the contact form will not deliver messages and the `/admin/` editor will not be able to log in.

## Customising

- Posts live in `content/blog/` as Markdown files with front matter (title, date, tags, image).
- Site name, URL and description are set at the top of `gatsby-config.js`.
- To change the logo, replace `static/logo.png` and run `npm run generate-favicon`.

## Status

Working template, last updated in 2020. It uses old dependency versions (Gatsby 2, Tailwind 1), so expect to need an older Node.js version and some npm warnings.

Planned ideas from the original author: highlighting the active menu item, a configurable menu bar and analytics.

## Credits and license

This project builds on the Gatsby blog template by [Raymond Yeh](https://geek.sg) ([yehjxraymond/gatsby-blog](https://github.com/yehjxraymond/gatsby-blog)). It is released under the MIT license, see `LICENSE`.
