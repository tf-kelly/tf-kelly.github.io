# Personal site — Thomas Kelly (tech aesthetic)

Five static pages + one stylesheet. Inter typeface, cool palette, system-aware dark mode. No build step, no framework.

## Files

```
index.html              Home (banner, bio, icon row, recent work)
publications.html       Articles, in-prep, public-facing, talks
teaching.html           Teaching record
misc.html               Greek karaoke + essays
style.css               All styling (light + dark mode)
```

## Files you need to add yourself

```
papyrus.jpg                       Banner image — P.Berol. 11529 v. crop
portrait.jpg                      Your photo
cv.pdf                            Your CV
mildenhall.pdf                    The refereeing essay
karaoke/high-school-musical.pdf   Greek translation
karaoke/dont-stop-me-now.pdf      Greek translation
karaoke/for-good.pdf              Greek translation
karaoke/dancing-queen.pdf         Greek translation
```

The placeholder `papyrus.jpg`, `portrait.jpg`, and `cv.pdf` already in this folder are dummies — replace them with the real files. Karaoke PDFs and `mildenhall.pdf` are not included; add them or the links will 404.

## Notes specific to this version

- **Dark mode** follows the visitor's OS setting automatically (via `prefers-color-scheme`). No toggle — it just matches their system. To see both, switch your OS between light and dark appearance.
- **Typeface:** Inter for Latin text, Noto Sans for Greek. Greek runs are wrapped in `<span lang="grc">…</span>` (or `<em lang="grc">`) so the polytonic accents render correctly — when you add new Greek text anywhere, wrap it the same way.
- **Accent colour:** cool blue (`#2563a8` light / `#6cb0ff` dark). Change `--accent` in the `:root` block of `style.css` to adjust.
- **Tag chips** (`forthcoming`, `under review`, `in prep`) on the home page use `<span class="tag">`. Add or remove as work changes status.
- **Banner image** has rounded corners and a max height of 240px; it's cropped via `object-fit: cover`. If your crop is a different shape, adjust `.banner img` in the CSS.

## Deploying

Same as any static site. To replace what's currently at `tf-kelly.github.io`: drop these files into the repo (via GitHub Desktop or the web UI), commit, push. The new files overwrite the old ones with the same names. The old serif `style.css` is fully replaced by this one.

For a custom domain, see GitHub Pages settings → Custom domain, and add the four A records + www CNAME at your registrar (as before).

## Reverting

If you decide against this version, your previous serif site is unaffected until you push these files. Keep a copy of the old `style.css` and HTML somewhere if you want to be able to switch back easily.
