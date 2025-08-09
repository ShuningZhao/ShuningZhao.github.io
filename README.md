# Shuning Zhao – Personal Academic & Project Website

This repository contains the source for my personal academic website built with **Hugo Blox Builder (Academic theme)**.

Live site: (update after deployment)  
Hugo version: 0.119.0 (see Netlify/GitHub Actions config)

## Features

- Academic CV style landing page
- Publications (imported from BibTeX; see `content/publication/`)
- Projects (e.g. Conveyancing Contract Reviewer)
- Talks & Events
- Blog posts
- Multilingual-ready
- Automatic build & deploy via GitHub Pages workflow (`.github/workflows/publish.yaml`) or Netlify (`netlify.toml`)

## Repository Structure (selected)

- `content/` — Markdown content (posts, publications, events, authors, projects)
- `config/_default/` — Core configuration:
  - Site: [config/_default/hugo.yaml](config/_default/hugo.yaml)
  - Params/UI: [config/_default/params.yaml](config/_default/params.yaml)
  - Menus: [config/_default/menus.yaml](config/_default/menus.yaml)
  - Modules: [config/_default/module.yaml](config/_default/module.yaml)
- `data/` — Extra data (e.g. [data/page_sharer.toml](data/page_sharer.toml))
- `assets/` — Pipeline assets (custom CSS/JS if added)
- `static/` — Static files served as-is (uploads, images)
- `theme.toml` — Theme metadata
- Workflows: `.github/workflows/`

## Prerequisites

- Go (for Hugo Modules) — currently `go 1.15` declared in [go.mod](go.mod) (you may upgrade locally if desired)
- Hugo Extended v0.119.0

Verify:
```
hugo version
go version
```

## Getting Started (Local Development)

```
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
hugo mod tidy        # Ensure modules resolved
hugo server -D       # -D includes drafts
```

Visit: http://localhost:1313

## Adding Content

Create a new blog post:
```
hugo new content/post/my-new-post/index.md
```

Create a project:
```
hugo new content/project/my-project/index.md
```

Create a publication manually:
```
hugo new content/publication/short-slug/index.md
```

Or import from a BibTeX file (`publications.bib`) — commit/update the file and the workflow [Import Publications From Bibtex](.github/workflows/import-publications.yml) will open a PR.

## Drafts vs Published

Front matter:
```
draft: true   # not published
draft: false  # published
```

## Updating Base URL

Set production URL in [config/_default/hugo.yaml](config/_default/hugo.yaml):
```
baseURL: 'https://your-domain.example/'
```

For Netlify, the build command in [netlify.toml](netlify.toml) injects `-b $URL`.

## Deployment Options

### GitHub Pages
Automatic via [publish workflow](.github/workflows/publish.yaml):
- Push to `main`
- Workflow builds with Hugo and deploys to GitHub Pages environment

### Netlify
Add repository in Netlify UI. Netlify reads [netlify.toml](netlify.toml).

Local production build test:
```
hugo --gc --minify
```
Output in `public/` (ignored by git per [.gitignore](.gitignore)).

## Customization

- Navigation: [config/_default/menus.yaml](config/_default/menus.yaml)
- Homepage sections: [content/_index.md](content/_index.md)
- Author profile: [content/authors/admin/_index.md](content/authors/admin/_index.md)
- Social share buttons: [data/page_sharer.toml](data/page_sharer.toml)
- Theme appearance & analytics: [config/_default/params.yaml](config/_default/params.yaml)

## Adding Custom Styling

Create a file such as:
```
assets/css/custom.css
```
Then reference via site params or (for Reveal slides) `assets/css/reveal_custom.css` (example shown in slides content).

## Publications

Each publication folder includes:
- `index.md` (front matter + abstract)
- Optional `cite.bib` for BibTeX citation

Example: [content/publication/ICASSP2021/](content/publication/ICASSP2021/)

## Slides

Reveal.js slides: [content/slides/example/index.md](content/slides/example/index.md)

Serve locally and open the slide page URL.

## Contact Form

Configured in homepage contact block using Netlify form processing. Ensure:
```
form:
  provider: netlify
```
in the block at [content/_index.md](content/_index.md). Netlify will auto-detect on deploy.

## Updating Hugo Modules

```
hugo mod get -u ./...
hugo mod tidy
```

Commit resulting `go.mod` changes.

## License

Site theme licensed under MIT — see [LICENSE.md](LICENSE.md). Content (publications, posts, images) is owned by the author (adjust license notice in [config/_default/params.yaml](config/_default/params.yaml) if needed).

## Todo / Ideas

- Set real `baseURL`
- Add Google Analytics / Clarity IDs
- Enable math (`features.math.enable: true` in [config/_default/params.yaml](config/_default/params.yaml)) if required
- Add resume PDF to `static/uploads/` and uncomment menu entry
- Configure repository URL in params for "Edit this page" links

## Support

Theme docs: https://docs.hugoblox.com  
Community Discord: https://discord.gg/z8wNYzb

---
Generated from the original Academic theme README and customized for this personal