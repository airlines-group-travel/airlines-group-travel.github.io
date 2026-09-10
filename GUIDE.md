# Airlines Group Travel — GitHub Pages Site

Everything you need to run this site, in one document.

**Live at:** <https://airlines-group-travel.github.io>
**Repository:** `airlines-group-travel/airlines-group-travel.github.io`
**Main website:** <https://www.airlinesgrouptravel.com>

---

## 1. The one rule that shapes this whole site

GitHub's Pages limits state the service is:

> "not intended for or allowed to be used as a free web hosting service to run
> your online business, e-commerce site, or any other website that is primarily
> directed at either facilitating commercial transactions or providing
> commercial software as a service (SaaS)."

That is why this is a **brand profile and guides site**, not a second booking
funnel. It describes the company and hands every commercial action off to the
main website.

**Never add to this site:** a quote form, enquiry form or any lead capture;
prices, fares or a "book now" flow; payment anything.

**Fine to add:** who you are, what you do, accreditations, contact details,
informational guides, links to the real site. A company profile with an
educational blog is a normal, permitted use. A booking funnel is not, and GitHub
takes sites down for it without warning.

---

## 2. Replacing the site with this bundle

This bundle is the complete site. Uploading through GitHub's web interface
**overwrites** files at the same path but **does not delete** files that are no
longer needed, so a few old files have to go manually.

### Option A — command line (cleanest, replaces everything at once)

```bash
cd agt-pages
git init
git add -A
git commit -m "Consolidated site: blog collection, CMS, plain-HTML landing page"
git branch -M main
git remote add origin https://github.com/airlines-group-travel/airlines-group-travel.github.io.git
git push -u origin main --force
```

The `--force` makes the repository match this folder exactly — old files
disappear, nothing lingers.

### Option B — web interface

1. **Add file → Upload files**, then drag in **the folders themselves**
   (`_blog`, `_includes`, `_layouts`, `assets`) plus the loose files
   (`_config.yml`, `index.md`, `blog.html`, `robots.txt`, `README.md`,
   `GUIDE.md`, `Gemfile`). Folder names starting with `_` are the ones the
   uploader most often drops — check afterwards that all four are listed in the
   repository.

2. **Create `.pages.yml` by hand.** Add file → Create new file → type the
   filename `.pages.yml` exactly → paste in the contents of the `pages.yml`
   file supplied alongside this bundle. The leading dot makes it invisible in
   Finder, so dragging it will not work.

3. **Delete these three old files**, each via its ⋯ menu → Delete file:
   - `SETUP-GUIDE.md` — replaced by this document
   - `BLOG-GUIDE.md` — merged into this document
   - `assets/img/README.md` — **important:** this one is currently publishing as
     a live page at `/assets/img/` and appearing in your sitemap

Either way, GitHub rebuilds in about a minute. Watch the **Actions** tab for a
green tick.

---

## 3. Editing the site

Almost every word on the landing page, every link, and all the structured data
comes from **`_config.yml`**. Change a value there and the page text, the meta
tags and the JSON-LD all update together — they can never drift apart.

Your real contact details, founding year and postcode are already filled in.

Two things worth a second look:

- **`founding_year: "2022"`** — this is published as `foundingDate` in your
  structured data and shown as "operating since" on the page. Confirm it matches
  the real incorporation year of Airfare Services USA LLC.
- **`show_address`** — 8 The Green, Suite A is a registered-agent address shared
  with thousands of other Delaware LLCs. It carries no local-SEO value and a
  sharp customer may recognise it. Set it to `false` to drop the address cleanly
  from both the page and the structured data, or swap in a genuine
  customer-facing office.

Prose and section order for the landing page live in `index.md`. **That file is
plain HTML with every tag at column 0, on purpose.** Kramdown turns any line
indented four or more spaces into a code block, which makes raw `</div>` tags
appear as visible text on the live page — that is exactly what happened before.
Edit the words between the tags; do not indent the tags and do not add
`markdown="1"` attributes.

Brand colours are the `:root` block at the top of `assets/css/style.css`.

---

## 4. Images

Two files still need to go into `assets/img/`:

| File | Size | Where to get it |
|---|---|---|
| `logo.png` | 284 × 77 | The same file the main site uses at `/public/assets/images/site-logo.png` |
| `favicon.png` | 32 × 32 | A square crop of the logo mark |

Use the **identical** logo file the main site uses — both properties then point
at visually identical logos, which is one more small confirmation that they are
the same company. If the dimensions differ, update `logo_width` and
`logo_height` in `_config.yml` to the real numbers; schema.org image dimensions
that do not match the actual file are a validation warning.

Until `logo.png` exists, your structured data points at a missing image and
social shares have no preview. It currently 404s.

---

## 5. The blog

Guides live at **`/blog/`** and are called *Group Travel Guides*. Each one is a
file in `_blog/`, but you will not touch those by hand.

### Where your content should actually go

**Publish your best writing on airlinesgrouptravel.com, not here.**

This site has no domain authority. An article published here ranks far worse
than the same article on the main site, and it consumes writing effort the main
site badly needs. The September audit found ~230 airline pages stuck around
position 13.5, largely because internal linking is thin — every guide published
on the main site that links into those pages helps them. A guide published here
does not.

Use this blog for one of three things and nothing else:

- **Overflow** — something written but not scheduled for the main site's CMS.
- **Content genuinely different in kind** — process explainers, terminology,
  "how this industry works" pieces that would sit oddly on a commercial blog.
- **A staging ground** — draft here, move the good ones to the main site.

**Never publish the same article in both places.** Duplicating your own content
across domains gives Google a reason to pick one and ignore the other, and the
one it picks will not be the github.io copy.

### One-time: connect the admin

1. Go to **<https://app.pagescms.org>** and sign in with GitHub.
2. Install the Pages CMS GitHub App on the **airlines-group-travel** organisation.
3. Grant it access to **this repository only**.
4. Select the repo. It reads `.pages.yml` and builds the editor.

Nothing to install, nothing to host. Pages CMS commits to the repository on your
behalf and GitHub rebuilds the site.

To give someone else publishing access: invite them to the organisation with
write access to the repo, then have them repeat step 1.

### Writing a guide

Click **Guides → Add an entry**. Every field carries an inline hint in the
editor; this is the same guidance in full.

**URL slug** *(required)* — becomes the filename and the address,
`/blog/your-slug-here/`. Lowercase letters, numbers and hyphens only. Three to
six words. **Once published, never change it** — the old address 404s and loses
any links or rankings it had earned.

**Page title** *(required)* — the H1 readers see, and the search-result title
when under 60 characters. Write it for a person and front-load the specific
thing the guide covers. `Group Booking Deposits and Name Deadlines, Explained`,
not `Group Travel Tips | Cheap Group Flights | Book Now`.

**SEO title** *(optional)* — only fill this in when the page title is too long
or too conversational for a search result. Under 60 characters. **Do not add the
site name**; it is appended automatically.

**Meta description** *(required)* — the grey summary under the title in Google
and the preview text when the link is shared. 120–160 characters, a real
sentence, specific to this guide. It also appears on the page as the standfirst
under the headline, so write something you are happy to have read aloud.

**Publish date** *(required)* — feeds `datePublished` and orders the list. Set
it to the day you publish; do not backdate.

**Author** — leave as the company name unless you have a genuinely named author
with a real bio to point at. A fake byline is worse than a company byline.

**Hero image + alt text** — optional, but it becomes the social share preview.
Landscape, at least 1200 × 675. **Compress it first** — anything over ~200 KB
slows the page and it is the first thing that loads. Alt text describes *what is
in the picture*, for screen reader users and image search: "Passengers boarding
a widebody aircraft at dusk", not "group travel booking cheap flights".
Keyword-stuffed alt text is an accessibility failure and does nothing for
ranking. Required whenever there is an image.

**Published** — turn off to keep a draft out of the guides list, the sitemap and
the feed. The file stays in the repository. To unpublish something later, switch
this off; do not delete the file, or the URL 404s.

**Content** — start at **Heading 2**; the page title is already the H1 and a
second one confuses the page outline. H2 for sections, H3 beneath them. Add alt
text to every image you insert. **Link out to the main site** wherever a reader
would want to act on what they just read — the relevant airline page, the
business class page, the deals page. That is the single most useful thing a
guide here can do.

### What happens automatically

You never have to think about: `<title>`, meta description, canonical URL, Open
Graph and Twitter Card tags, `BlogPosting` structured data with real dates,
`BreadcrumbList` structured data plus visible breadcrumbs, the sitemap entry,
the RSS entry, the sort order, and the call-to-action block at the foot of every
guide. All of it derives from the fields above, so there is exactly one JSON-LD
block per page and it can never contradict what is visible.

---

## 6. Connecting it back to the main site

This is what turns a page into a signal. Skipping it wastes the exercise.

**6a. Add this URL to the main site's `sameAs`.** Your main site's `Organization`
structured data lists seven profiles. Add an eighth:

```
https://airlines-group-travel.github.io
```

It belongs in `app/Support/Schema.php` alongside the others. The schema rebuild
specced on 3 September has still not been deployed — add this URL to that
rebuild rather than making it a separate job.

Why it matters: this site already declares its Organization `@id` as
`https://www.airlinesgrouptravel.com/#organization` — deliberately the *main
site's* identifier, not its own. Once the main site also names this URL in
`sameAs`, the two properties point at each other and search engines read one
company across two domains. One-way linking does about half as much.

**6b. Add the URL to your public profiles** — LinkedIn company page, the GitHub
organisation profile, Crunchbase. Corroboration from independent sources is the
entire mechanism.

**6c. Verify in Google Search Console.**

1. Go to <https://search.google.com/search-console> and sign in.
2. **Add property** → choose the **URL prefix** box on the right (not Domain —
   Domain verification needs DNS access, and you do not control `github.io` DNS).
3. Enter exactly: `https://airlines-group-travel.github.io/`
4. Expand **HTML tag** under "Other verification methods". Google shows a line like
   `<meta name="google-site-verification" content="AbC123xyz..." />`
5. Copy **only the content value** — the part between the quotes, not the whole tag.
6. In `_config.yml`, paste it into `google_site_verification: ""` and commit.
7. Wait about a minute for the rebuild, then click **Verify** in Search Console.

Why the config key rather than the HTML-file method: the tag is emitted on every
page from one setting, and it survives every rebuild and every force-push. An
uploaded `google*.html` file is one bad `--force` away from vanishing and
silently un-verifying the property.

**Then submit the sitemap.** Search Console → **Sitemaps** → enter `sitemap.xml`
→ Submit. It is generated at build time; never create one by hand.

**Then request indexing on the homepage.** Paste the homepage URL into the search
bar at the top of Search Console → **Request indexing**. Do this once for the
homepage and once for `/blog/`. Do not request it repeatedly — it does not speed
anything up and the daily quota is small.

Bing Webmaster Tools works identically via `bing_site_verification` in the same
config file, and can import your Search Console setup in one click.

**6d. Check the structured data.** Paste the live URL into
<https://validator.schema.org> — expect zero errors and zero warnings. Then
<https://search.google.com/test/rich-results> — the landing page will report *no
eligible rich results*, which is correct, since it deliberately carries no
Article, Review, Offer or price markup. A blog post should report **Breadcrumbs**
as eligible.

---

## 6b. Index-readiness checklist

Verified live on 10 September 2026. Re-run these any time you change the setup.

| Check | Status | How to re-check |
|---|---|---|
| `robots.txt` present, allows all crawlers | Pass | Load `/robots.txt` |
| `robots.txt` points at the sitemap | Pass | Same file, last line |
| `sitemap.xml` generated, right domain | Pass | Load `/sitemap.xml` |
| Sitemap contains all real pages, no junk | Pass — 3 URLs | Same |
| No `X-Robots-Tag: noindex` header | Pass | DevTools → Network → click the page → Response Headers |
| `<meta name="robots">` says index, follow | Pass | View source, or DevTools → Elements |
| Canonical URL on every page, correct domain | Pass | View source |
| One `<h1>` per page | Pass | DevTools console: `document.querySelectorAll('h1').length` |
| Exactly one JSON-LD block per page | Pass | `document.querySelectorAll('script[type="application/ld+json"]').length` |
| `lang="en"` on `<html>` | Pass | View source |
| Real 404s return HTTP 404 | Pass | Load any nonsense URL |
| 404 page is noindex and out of the sitemap | Pass | `/404.html` source |
| Meta descriptions under 160 characters | Pass | Per page |
| Every `<img>` has an alt attribute | Pass | `[...document.images].filter(i=>!i.hasAttribute('alt')).length` |
| `logo.png` and `favicon.png` exist | **FAIL — both 404** | Load `/assets/img/logo.png` |

The last one is the only outstanding item. `og:image` on every page points at
`/assets/img/logo.png`, so until that file exists, every link shared to Facebook,
LinkedIn or X renders without a preview image, and the `logo` in your
Organization structured data references a missing file.

## 7. What this site does for you, honestly

**What it does.** It is an independent, verifiable statement of who your company
is, on a domain you do not own, using the same entity identifier as your main
site. Search engines build a picture of a business from corroborating mentions
across independent properties, and this adds one more consistent, well-formed
source — the same job your LinkedIn and Trustpilot profiles already do. It is
also a permanent URL you control that still resolves if the main site is ever
mid-migration.

**What it does not do.** `github.io` is on the Public Suffix List, so browsers
and search engines treat every `*.github.io` subdomain as its own separate site.
This page inherits **none** of github.com's domain authority. The link back to
the main site is a real followed link from a brand-new site with no authority,
which is worth very close to nothing as a ranking signal. Anyone who tells you a
GitHub Pages site will move your Domain Rating is selling something.

This is entity and brand work, not link building. Judged against the September
audit it is far less valuable than fixing the ~230 airline pages at position 13.5,
deploying the schema rebuild, or building the page-aware language switcher. Do it
because it is cheap and permanent, not instead of those.

---

## 8. What not to do

**Do not build more of these.** One official branded property is a normal
corporate footprint. Several thin sites on `github.io`, `gitlab.io`,
`netlify.app` and similar, all linking back with keyword-rich anchors, is a link
scheme under Google's spam policies and carries real risk of a manual action. The
value here comes entirely from this being genuine and singular.

**Do not copy content from the main site.** Duplicating your own pages across
domains gives search engines a reason to pick one and ignore the other.

**Do not stuff keywords.** The page names the services and links to them. That is
sufficient.

**Do not let it go stale.** A profile listing a disconnected phone number is
worse than no profile. Check it whenever the main site's contact details,
accreditations or social profiles change.

---

## 9. Adding a plain page

Anything that is not a guide — a terms page, a longer explainer — is a Markdown
file in the repository root:

```markdown
---
layout: default
title: "Your Page Title"
description: "One sentence, under 160 characters."
permalink: /your-page/
---

## A heading

Normal Markdown from here.
```

Commit it and it is live at `/your-page/` in about a minute, with the header,
footer, styling, meta tags and sitemap entry all handled. Give every page a
genuinely different title and description.

Do not add these through Pages CMS — it is configured for the guides collection
only. And do not copy the structure of `index.md`; that is hand-written HTML for
the landing page specifically.

---

## 10. Troubleshooting

**Actions shows a red X.** Click the failed run and read the log. It is almost
always a YAML error in `_config.yml` — a smart quote pasted from Word, a colon
inside an unquoted value, or a lost indent. Paste the file into
<https://www.yamllint.com> to find the line.

**Page loads but has no styling, text left-aligned on white.** Either
`assets/css/style.css` did not upload, or `url` in `_config.yml` does not match
where the site is actually published. Check Settings → Pages for the real URL,
then load `/assets/css/style.css` directly — it should return CSS beginning with
a comment naming Airlines Group Travel.

**Raw `</div>` tags visible in the page text.** Something in `index.md` got
indented by four or more spaces. Kramdown reads that as a code block. Move the
tags back to column 0.

**404 at the site root.** The repository name must exactly match the owner name
plus `.github.io`, and the repository must be public on the Free plan.

**Changes not showing.** Hard refresh (`Cmd/Ctrl + Shift + R`) — GitHub caches
aggressively. If still stale after five minutes, check Actions for a failed build.

**`/feed.xml` returns 404.** The feed plugin's collection path is the one setting
here that could not be verified against a live build. Delete the
`<link rel="alternate" type="application/rss+xml" …>` line from
`_layouts/default.html` and the site is fine without it.

**Google has not indexed it after a month.** Normal for a new site with almost no
inbound links. Confirm it is verified in Search Console, request indexing on the
URL, and make sure section 6 is actually done — the inbound references are what
get it crawled.

---

## 11. File reference

| File | What it is | Edit it? |
|---|---|---|
| `_config.yml` | Every piece of text and every link on the landing page | **Yes — this is the one** |
| `index.md` | Landing page structure and prose. Plain HTML, tags at column 0 | Yes, the words only |
| `blog.html` | The `/blog/` index | Rarely |
| `_blog/` | One file per guide — managed through Pages CMS | Via the CMS |
| `_layouts/default.html` | Header, footer, all `<head>` meta tags | Rarely |
| `_layouts/post.html` | Single guide layout | Rarely |
| `_includes/schema.html` | All JSON-LD, generated from config and front matter | No |
| `assets/css/style.css` | All styling. Brand colours are the `:root` block | For colours |
| `assets/img/` | `logo.png` and `favicon.png` go here | Add your files |
| `.pages.yml` | Pages CMS admin configuration | To change the fields |
| `robots.txt` | Allows all crawlers, points at the sitemap | No |
| `Gemfile` | Local preview only — not needed to publish | No |
| `README.md` | Repository description shown on GitHub | Optional |
| `GUIDE.md` | This document | — |

`sitemap.xml` and `feed.xml` are generated by GitHub at build time. Do not create
either by hand — they will conflict.
