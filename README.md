# Personal site — Thomas Kelly

Five static HTML pages + one stylesheet. No build step, no framework, no dependencies. Everything is hand-edited, lives in git, deploys for free.

## Files in this folder

```
index.html              Home page
publications.html       Articles, in-prep, public-facing, talks
teaching.html           Teaching record
misc.html               Greek karaoke + essays
style.css               All styling
orcid.svg               Small ORCID icon for the contact block
```

Plus three things you need to add yourself:

```
papyrus.jpg             Sidebar image — P.Berol. 11529 v. crop
portrait.jpg            Your photo (from Magdalen page for now)
cv.pdf                  Your CV
```

## Before deploying — replace these placeholders

1. **ORCID iD.** Search `0000-0000-0000-0000` in `index.html` and replace both occurrences (the link target and the displayed text) with your actual ORCID iD.

2. **`papyrus.jpg`.** Download a high-res copy of the cropped diagram from <https://berlpap.smb.museum/03066/?lang=en> (the 600 dpi original is linked in the database record). Crop to roughly square or vertical-rectangle around the diagram you sent. Save as `papyrus.jpg` (or `.png` — if you change the extension, update `index.html`, `publications.html`, `teaching.html`, and `misc.html`).

3. **`portrait.jpg`.** Right-click-save the photo from your Magdalen page, save as `portrait.jpg`. The CSS displays it at ~180px wide; anything ≥360px should be fine.

4. **`cv.pdf`.** Drop in your CV.

5. **Mildenhall essay & karaoke links.** In `misc.html`, the four `[text]` and `[recordings]` links and the Mildenhall essay link are all `href="#"` (placeholders). Replace with real URLs once you've decided where to host the PDFs/recordings. Options: put the essay PDF in this same folder and link to `mildenhall.pdf`; host recordings on YouTube/SoundCloud and link out.

## Deploying to GitHub Pages

1. Create a new GitHub repository named `<your-username>.github.io` (the repo name matters — it's how GitHub Pages knows to serve at the root).
2. Upload all files in this folder to the root of the repo (drag-and-drop in the GitHub web UI is fine).
3. Go to repo Settings → Pages → Source → select "Deploy from a branch", Branch: `main`, Folder: `/ (root)`. Save.
4. Wait ~1 minute. Your site is live at `https://<your-username>.github.io`.

## Adding a custom domain

Once you've registered your domain (e.g. `thomas-kelly.co.uk`):

1. **At your registrar's DNS panel**, add the following records pointing to GitHub Pages:
   - Four A records for the apex (`@`) pointing to: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - One CNAME for `www` pointing to `<your-username>.github.io`
2. **In the GitHub repo**, Settings → Pages → Custom domain → enter `thomas-kelly.co.uk` (no `https://`, no `www`). Save.
3. **Wait** for DNS to propagate (minutes to a few hours). GitHub will show a green tick when it's verified.
4. **Tick "Enforce HTTPS"** once it's available (a few minutes after verification). Done.

The two changes will also create a `CNAME` file in your repo automatically — leave it alone.

## Editing later

Everything is plain HTML. To add a publication, open `publications.html`, copy an existing `<li>...</li>`, edit, save, commit. To add an essay or a song to Misc., the same. To change wording on the home page, edit `index.html`.

To change the colour palette or typography globally, edit the `:root` block at the top of `style.css`. The accent colour is `--accent: #6b3410` — change that one variable and every link on the site updates.

## Notes on the design

- **Typography:** EB Garamond loaded from Google Fonts. Has full polytonic Greek support, which is why the Greek titles on Misc. render correctly.
- **Layout:** Two-column on desktop, stacks on mobile (under 760px). The sidebar is sticky on desktop — it stays in place as you scroll the main content.
- **Colour:** white background, near-black text, warm-brown accent (`#6b3410`) sampled from the papyrus ink.
- **Sidebar image attribution** lives in two places: the `title` attribute on the image link (hover tooltip) and the footer. The footer mentions the Berlin papyrus collection by name.

## If something breaks

Check the browser console (right-click → Inspect → Console). 90% of the time it's a typo in a path. The site has no JavaScript, so genuine errors are rare.
