# Lean into QEC — tutorial website

Static site for the tutorial *Lean into QEC: Machine Verification for Quantum Error
Correction*, at IEEE Quantum Week 2026 (QCE26), Sunday September 13, 2026, Toronto.

Everything lives in `index.html` — HTML and CSS in one file, no build step, no
dependencies. Open it in a browser to preview; edit it in any text editor.

## Filling in the agenda

The agenda is the block marked `<!-- AGENDA -->` in `index.html`. Six placeholder
rows are already there. Each normal row looks like this:

```html
<tr>
  <td class="time">10:00 &ndash; 10:20</td>
  <td class="session">Session title
    <span class="note">Optional one-line note. Delete this span if unused.</span>
  </td>
  <td class="who">Presenter Name</td>
</tr>
```

A break row is the same but with `class="break"` on the `<tr>`, which greys and
italicizes it:

```html
<tr class="break">
  <td class="time">12:00 &ndash; 12:30</td>
  <td class="session">Break</td>
  <td class="who"></td>
</tr>
```

Copy, paste, and reorder rows freely — add as many as you need, delete the ones
you don't. Use `&ndash;` for the en dash between times so it renders correctly.

## Other placeholders

Anything still to be filled in is wrapped in `<span class="todo">…</span>`, which
renders as pink dashed-outline text so it's obvious at a glance. Search the file
for `TODO` to find them all. The current list:

- room number, once QCE26 announces it
- the QuantumErrorCorrectionLean repo URL
- slides, exercises, and setup-instruction links (or delete those rows)
- profile links for Stavan Jain and Nithin Raveendran (Aws Albarghouthi and
  Swamit Tannu are already linked)
- contact email, if you'd prefer an institutional address

When a placeholder is filled, delete the surrounding `<span class="todo">` and
`</span>` tags so the text renders normally. Once they're all gone you can also
delete the `.todo` rule from the stylesheet.

## Changing the look

The colours are CSS custom properties at the top of the `<style>` block. The one
worth changing is `--accent` (currently a dark red, `#9b2226`) — it drives the
eyebrow text, links, and TODO highlights. There's a `prefers-color-scheme: dark`
block near the bottom of the stylesheet with the dark-mode equivalents; if you
change `--accent`, change `--accent` there too (it wants a lighter tint of the
same hue).

`--maxw` controls the content column width, currently `46rem`.

## Publishing on GitHub Pages

Push these files to a repo, then in **Settings → Pages** set the source to
*Deploy from a branch*, branch `main`, folder `/ (root)`.

If it goes in the existing `qqq-wisc.github.io` repo alongside
`splash25-tutorial.html`, rename `index.html` to something like
`qce26-tutorial.html` and drop it at the repo root — it'll be served at
`https://qqq-wisc.github.io/qce26-tutorial.html`. In that case you don't need
`.nojekyll`, since that repo already has its own setup.

If it's a standalone repo, keep the name `index.html` and keep `.nojekyll` (it
tells Pages to serve the files as-is rather than running them through Jekyll).

## Files

```
index.html    the whole site
README.md     this file
.nojekyll     bypasses Jekyll processing on GitHub Pages
assets/       headshots or other images, if you decide to add them
```
