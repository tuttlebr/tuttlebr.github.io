# tuttlebr.github.io

My personal site — one static page, plain HTML + CSS, no build step. This README
is a cheat sheet for the edits I'll actually make, so I don't have to relearn the
markup each time.

Everything lives in two files:

- **`index.html`** — all the words and links.
- **`assets/css/styles.css`** — all the looks (colors, fonts, spacing).

---

## Preview my changes before publishing

```bash
cd /volume2/daedalus/datasets/tuttlebr.github.io
python3 -m http.server 8000
```

Open <http://localhost:8000>. Edit a file, save, refresh the browser. Stop the
server with `Ctrl+C`.

## Publish

GitHub Pages serves whatever is on the `main` branch. To go live:

```bash
git add -A
git commit -m "update site"
git push
```

It's live at <https://tuttlebr.github.io> within a minute or so.

---

## Common edits

### Change the intro line or the "about" blurb

In `index.html`, the headline line is inside the `whoami` block (the `<p class="lede">`),
and the paragraph is inside the `cat about.txt` block (the `<p>` in its `.output`).
Just change the text between the tags — leave the tags alone.

### Add a project

Each project under `ls ~/work` is one `<li class="entry">` block in `index.html`.
Copy this, paste it into the `<ul class="listing">`, and fill in the four bits:

```html
            <li class="entry">
              <div class="entry-head">
                <a class="entry-name" href="https://github.com/tuttlebr/REPO-NAME">REPO-NAME</a>
                <span class="leader" aria-hidden="true"></span>
                <span class="entry-lang">LANGUAGE</span>
              </div>
              <p class="entry-desc">
                One or two plain sentences about what it does.
              </p>
            </li>
```

Order on the page = order in the file. Move a block up to feature it.

### Remove a project

Delete its whole `<li class="entry"> … </li>` block.

### Add or change a link (e.g. add email)

Links live in the `cat contact.txt` block as `<li>` items. To add email, paste:

```html
            <li><a href="mailto:btuttle@nvidia.com">btuttle@nvidia.com</a></li>
```

(Heads up: a `mailto:` address on a public page gets scraped by spammers. I left
email off on purpose — only add it if I've decided that's fine.)

---

## Changing the look (in `assets/css/styles.css`)

### Colors and fonts — all at the top

The whole palette is the `:root` block at the very top of the file. Change a hex
value to recolor the whole site:

```css
  --paper:  #fbfaf7;   /* page background */
  --ink:    #1a1a18;   /* main text */
  --muted:  #6b6b66;   /* descriptions, tags, footer */
  --line:   #e5e2da;   /* hairlines, dotted leaders */
  --accent: #a85410;   /* the $ prompt, blinking cursor, link hover */
```

Tip: if I make `--accent` brighter/lighter, check it's still readable on the
paper background (aim for a contrast ratio of at least 4.5:1).

The two typefaces are `--mono` (JetBrains Mono — headings + prompts) and `--sans`
(Inter — body), also in that `:root` block. They're loaded from Google Fonts via
the `<link>` near the top of `index.html`; if I swap a font name here, update that
link too.

---

## What's in the repo

```
index.html            the page
404.html              not-found page (same style)
assets/css/styles.css all styling
assets/img/favicon.png the "BT" favicon
```
