# Alex Chudakov — personal website

One long scrolling page. Static HTML, no build step, no dependencies.

## Publish on GitHub Pages

1. Create a repository (e.g. `alexchudakov.github.io` or `personal-site`).
2. Upload everything in this folder to the repository root.
3. Settings → Pages → Source: **Deploy from a branch**, branch `main`, folder `/ (root)`.
4. The site goes live in a minute or two.

`.nojekyll` is included so GitHub serves the files as-is.

## Files

- `index.html` — the entire site (markup, styles, and scripts)
- `images/` — photographs
- `files/` — PDFs (résumé, program, certificates)

## Updating

**Colors.** Every color is a CSS variable on the root `<div data-root>` near the top of `index.html`:
`--accent` is the clay-court orange, `--bg`/`--fg` are the bone-white background and ink text, and `--s0`…`--s8` are the nine section bands, in scroll order. Change one value and it updates everywhere.

**Adding a photo.** Find the dashed placeholder block for that slot and replace its inner content with an `<img>`:

```html
<div style="position:relative;overflow:hidden;min-height:340px">
  <img src="images/tennis-action.jpg" alt="Alex serving during a tournament match"
       style="width:100%;height:100%;object-fit:cover;display:block">
</div>
```

**Adding a video.** Replace a video placeholder with an embed:

```html
<div style="position:relative;padding-top:56.25%">
  <iframe src="https://www.youtube.com/embed/VIDEO_ID" title="Match video" frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; picture-in-picture"
          allowfullscreen style="position:absolute;inset:0;width:100%;height:100%"></iframe>
</div>
```

**Links to fill in.** Search `index.html` for `href="#projects"` and `href="#publishing"` and swap in the real URLs: TennisAC live site, the GitHub repository, the published article, and `files/resume.pdf`.

**Adding a section.** Copy an existing `<section>`, give it a new `id` and `data-section` value, add a matching `<a href="#id" data-nav="id">` in the nav, and pick the section band colors with `--s` variables so the color still flows into its neighbours.

**Motion.** All scroll behavior lives in the single `<script>` at the bottom: reveal-on-scroll, active nav highlighting, and the progress bar. It respects `prefers-reduced-motion`.
