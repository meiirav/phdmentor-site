# PhDMentor.org

Source for the PhDMentor site, built with Jekyll + Minimal Mistakes
(loaded as a remote theme, so this repo only contains your content and
customizations — not the theme's own files).

## 1. Before you push: things to fill in

Search the project for `TODO` and replace:
- `_config.yml` — your real name, contact email, timezone
- `_pages/book.md` — your actual Calendly URL
- Placeholder images in `assets/images/` — swap the `.svg` placeholders for
  a real headshot and hero photo once you have them (same filenames will
  work with no other changes, or update the paths in `_config.yml`,
  `index.md`, and the page front matter if you rename files)

## 2. Create the GitHub repository

1. Go to github.com and create a **new repository** (not a fork), e.g.
   `phdmentor-site`. It does *not* need to be named `username.github.io` —
   that naming convention is only required for a user's default/root Pages
   site. A project repo works fine for a custom domain.
2. Push this project to it:
   ```bash
   cd phdmentor-site
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/phdmentor-site.git
   git push -u origin main
   ```

## 3. Enable GitHub Pages

1. In the repo, go to **Settings → Pages**.
2. Under "Build and deployment", set **Source** to "Deploy from a branch".
3. Set **Branch** to `main`, folder `/ (root)`.
4. Save. GitHub will build and publish the site at
   `https://YOUR-USERNAME.github.io/phdmentor-site/` within a few minutes.

Note: this setup uses GitHub's built-in Jekyll build (no GitHub Actions
needed) — the `remote_theme` and plugins used here
(`jekyll-remote-theme`, `jekyll-paginate`, `jekyll-sitemap`, `jekyll-feed`,
`jekyll-include-cache`) are all on GitHub Pages' supported plugin
allowlist, so this will build correctly without any custom workflow.

## 4. Point your custom domain (phdmentor.org) at it

The `CNAME` file in this repo already tells GitHub to serve this site at
`phdmentor.org`. You still need to configure DNS at your domain registrar
(wherever you bought phdmentor.org):

**For the apex domain (`phdmentor.org`)**, add four `A` records pointing to
GitHub Pages' IP addresses:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**For `www.phdmentor.org`** (recommended, so both work), add a `CNAME`
record:
```
www.phdmentor.org  →  YOUR-USERNAME.github.io
```

Then back in **Settings → Pages** on GitHub, enter `phdmentor.org` as your
custom domain and enable "Enforce HTTPS" once it becomes available (can
take up to 24 hours after DNS propagates).

## 5. Preview locally before pushing changes (optional but recommended)

If you have Ruby installed:
```bash
bundle install
bundle exec jekyll serve
```
Then visit `http://localhost:4000`. Note: pagination on `/blog/` may not
fully behave locally in all Jekyll versions — always double check the live
site after pushing if you rely on it.

## 6. Ongoing content edits

- **New blog post**: add a file to `_posts/` named
  `YYYY-MM-DD-your-title.md`, following the front matter pattern in the
  existing sample post.
- **Edit a static page** (About, How It Works, Book): edit the
  corresponding file in `_pages/`.
- **Change nav menu**: edit `_data/navigation.yml`.
- **Change colors**: edit the palette variables at the top of
  `assets/css/main.scss`.
- **Homepage "From the Blog" section**: shows up to 3 posts. By default it
  shows your 3 most recent posts automatically. If you'd rather hand-pick
  which posts appear (e.g. once you have enough posts that "newest" isn't
  always "best for a first-time visitor"), add `featured: true` to the
  front matter of up to 3 posts — the homepage will then show only those,
  instead of the most recent ones. Remove the flag (or set it on different
  posts) any time to change the selection.
- **Turning the homepage blog section off entirely**: set
  `show_blog_on_home: false` in `_config.yml`. The blog itself keeps
  running at `/blog/` and stays in the nav — this only removes it from the
  homepage, e.g. if coaching becomes the clear headline offering and the
  blog moves to a supporting role. Set it back to `true` any time.

Every push to `main` triggers a rebuild automatically — no extra steps
needed.
