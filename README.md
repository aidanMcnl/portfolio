# Jekyll Portfolio (GitHub Pages Compatible)

A fully Markdown-driven portfolio using Jekyll collections for projects and publications. Compatible with GitHub Pages (no custom plugins; uses the `github-pages` gem).

## Local Preview

1. Install Ruby and Bundler.
2. Install dependencies:
   ```bash
   bundle install
   ```
3. Serve locally:
   ```bash
   bundle exec jekyll serve --livereload
   ```
4. Open `http://127.0.0.1:4000`.

Note: If you encounter a WEBrick error on Ruby 3, run:
```bash
bundle add webrick
```

## Structure

- `index.md`: Home page
- `about.md`: About page
- `_projects/`: Project items (Markdown)
- `projects/index.md`: Projects listing page
- `_publications/`: Publication items (Markdown)
- `publications/index.md`: Publications listing page
- `_layouts/`: Layout templates (`default`, `collection`)
- `assets/css/site.css`: Global styles
- `_config.yml`: Jekyll configuration
- `CNAME`: Custom domain (optional)

## Add a Project

1. Create a new file under `_projects/` named like `my-project.md` with front matter:
   ```yaml
   ---
   title: "My Project"
   date: 2025-01-01
   summary: "One line summary."
   tags: [tag1, tag2]
   repo: "https://github.com/yourname/my-project"
   demo: "https://example.com/my-project"
   ---
   
   Markdown body describing the project.
   ```
2. The project will appear on `/projects/` sorted by `date` (newest first).

## Add a Publication

1. Create a new file under `_publications/` named like `paper-2025.md` with front matter:
   ```yaml
   ---
   title: "Paper Title"
   authors: ["Doe, Jane", "Smith, John"]
   year: 2025
   venue: "Conference Name"
   doi: "10.1234/abcd"
   url: "https://example.com/paper"
   pdf: "https://example.com/paper.pdf"
   ---
   
   Optional abstract or notes here.
   ```
2. The publication will appear on `/publications/` grouped by `year` (newest first).

## GitHub Pages Deployment

- Push this repository to GitHub.
- In GitHub, go to Settings → Pages and choose the `main` branch (root) as the source.
- If using a custom domain, set it in the Pages settings to match the `CNAME` file.

## Custom Domain (GoDaddy)

1. In GitHub → Settings → Pages, set your custom domain (e.g., `example.com`).
2. In GoDaddy DNS:
   - Create `A` records pointing `@` to GitHub Pages IPs:
     - 185.199.108.153
     - 185.199.109.153
     - 185.199.110.153
     - 185.199.111.153
   - Create a `CNAME` record for `www` pointing to `<your-username>.github.io`.
3. Wait for DNS to propagate, then verify the domain in GitHub Pages. Enable HTTPS.

## Notes

- Keep content in Markdown; no non-whitelisted plugins are used.
- Collections: `projects` and `publications` are output as pages.
