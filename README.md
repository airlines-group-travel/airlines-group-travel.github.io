# airlines-group-travel.github.io

Official GitHub Pages company profile for **Airlines Group Travel**
(Airfare Services USA LLC) — group air travel for 10 or more passengers.

**Live site:** https://airlines-group-travel.github.io
**Main website:** https://www.airlinesgrouptravel.com

---

## What this is

A company profile plus a small guides blog. Informational only — all quotes,
bookings and support happen on the main website.

## Editing

Almost everything comes from **`_config.yml`**. Change a value there and the page
text, the `<head>` meta tags and the JSON-LD structured data all update together.

Blog guides are written through **[Pages CMS](https://app.pagescms.org)**, which
reads `.pages.yml` and commits to this repository.

Built with Jekyll. GitHub builds and deploys on every push to `main`.

## Structure

```
_config.yml              all site content and settings
index.md                 landing page (plain HTML — do not indent the tags)
blog.html                the /blog/ index
_blog/                   one file per guide
_layouts/                default.html, post.html
_includes/schema.html    JSON-LD, generated from config + front matter
assets/css/style.css     styles
assets/img/              logo.png, favicon.png
.pages.yml               Pages CMS admin configuration
robots.txt               crawler directives
```

`sitemap.xml` and `feed.xml` are generated at build time.

## Documentation

See **`GUIDE.md`** — setup, editing, publishing guides, SEO rules and
troubleshooting, all in one place.
