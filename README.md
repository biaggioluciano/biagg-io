# Biagg.io — Hugo Site

## Quick start

```bash
# 1. Install Hugo (Mac)
brew install hugo

# 1. Install Hugo (Windows)
winget install Hugo.Hugo.Extended

# 2. Enter the project folder
cd biagg-io

# 3. Start local dev server
hugo server -D

# 4. Open in browser
# → http://localhost:1313
```

## Writing a new post

```bash
# New blog post
hugo new blog/my-post-title.md

# New OS post
hugo new one-system/my-post-title.md

# New Weekly Geeky
hugo new weekly-geeky/2026-03-15.md

# New recommendation
hugo new recommendations/something-i-liked.md
```

Each new file opens with `draft: true` — change to `draft: false` when ready to publish.

## Adding "Interesting reads" to a Weekly Geeky post

In the front matter of any `weekly-geeky/` post, add:

```yaml
reads:
  - title: "Article title"
    author: "Author Name"
    url: "https://example.com"
    source: "example.com"
    date: "2026.03.08"
```

These will auto-populate the homepage sidebar.

## Adding a thumbnail image

Put your image in `static/img/`, then reference it in the post front matter:

```yaml
image: /img/my-post-image.jpg
```

## Building for production

```bash
hugo
# Output is in the /public folder — upload this anywhere
```

## Deploying (free)

**Netlify** (easiest):
1. Push this folder to a GitHub repo
2. Connect repo to netlify.com
3. Set build command: `hugo`
4. Set publish directory: `public`
5. Every git push auto-deploys ✓

**Cloudflare Pages** (fastest CDN):
Same steps as Netlify but at pages.cloudflare.com

## Folder structure

```
biagg-io/
├── hugo.toml              # Site config, menu, settings
├── content/
│   ├── blog/              # Blog posts
│   ├── one-system/        # OS section posts
│   ├── weekly-geeky/      # Weekly Geeky posts
│   └── recommendations/   # Recommendations
├── layouts/
│   ├── index.html         # Homepage layout
│   ├── _default/
│   │   ├── baseof.html    # Base HTML shell
│   │   ├── single.html    # Single post view
│   │   └── list.html      # Section index view
│   └── partials/
│       └── nav.html       # Navigation bar
├── static/
│   └── css/
│       └── main.css       # All styles
└── archetypes/
    ├── default.md         # Default new post template
    └── weekly-geeky.md    # Weekly Geeky template
```
