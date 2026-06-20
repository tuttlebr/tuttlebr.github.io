# tuttlebr.github.io

My personal site. A single static page — plain HTML and CSS, no build step, no
analytics, no third-party widgets. It's styled as a small terminal session and
points at the projects I'm actually working on.

## Files

- `index.html` — the page.
- `404.html` — not-found page, same style.
- `assets/css/styles.css` — all styling.
- `assets/img/favicon.png` — favicon.

Type is [Inter](https://rsms.me/inter/) (body) and
[JetBrains Mono](https://www.jetbrains.com/lp/mono/) (headings, prompts),
loaded from Google Fonts.

## Editing locally

There's no build step — edit the files and open `index.html`, or run a local
server:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Publishing

GitHub Pages publishes from the repository root. The public URL is
`https://tuttlebr.github.io`.

## Editing the project list

Each project under `ls ~/work` is an `<li class="entry">` in `index.html`: a
linked repo name, a language tag, and a one-line description. Copy a block to
add one; delete a block to remove one.
