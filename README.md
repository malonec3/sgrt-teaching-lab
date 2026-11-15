# SGRT teaching lab

Two self-contained, offline-capable teaching simulators for surface-guided radiotherapy (SGRT), served from one page with two tabs.

| Tab | File | What it is |
|---|---|---|
| 1 · Teaching cases | `teaching-cases.html` | v4: five guided teaching cases (flat surface, chest wall vs breast, face ROI choice, local change vs ROI size, noise vs calibration) plus the Advanced full simulator. |
| 2 · Patient simulator | `patient-simulator.html` | v5: one supine patient; paint an ROI anywhere, then test a known shift (over several simulated days) or 60 s of treatment with breathing, drift and a sudden move. |

`index.html` is a thin shell: it shows the two tabs and loads each simulator in its own frame. The simulators themselves are unchanged and also work on their own (the "Open full screen" links in the top bar).

Links you can give students once deployed:

- `…/` or `…/index.html#cases` — opens on the teaching cases
- `…/index.html#patient` — opens on the patient simulator
- `…/teaching-cases.html` and `…/patient-simulator.html` — each simulator alone, full screen (good for projecting)

## Deploying on GitHub Pages

You need a GitHub account. GitHub Pages is free for **public** repositories (private repositories need a paid plan).

### A. Using the GitHub website only (no git required)

1. Sign in at github.com and click **New repository** (the `+` at the top right).
   - Repository name: e.g. `sgrt-teaching-lab`
   - Visibility: **Public**
   - Tick **Add a README file** (so the repository is not empty), then **Create repository**.
2. On the repository page click **Add file → Upload files**. Drag in all the files from this folder:
   `index.html`, `teaching-cases.html`, `patient-simulator.html`, `README.md` (this one replaces the generated one) and `.nojekyll`.
   Click **Commit changes**.
   - If your file browser hides `.nojekyll` (it is a dot-file), it is optional: it only tells GitHub not to run its Jekyll processor, which is harmless for plain HTML either way.
3. Open **Settings → Pages** (left-hand menu, "Code and automation" section).
   - Under **Build and deployment → Source** choose **Deploy from a branch**.
   - Branch: **main**, folder: **/ (root)**. Click **Save**.
4. Wait a minute or two, then refresh the Pages settings page. It shows **"Your site is live at https://<your-username>.github.io/sgrt-teaching-lab/"**. That is the link to share.

### B. Using git from a terminal

```bash
cd path/to/this/folder
git init
git add index.html teaching-cases.html patient-simulator.html README.md .nojekyll
git commit -m "SGRT teaching lab"
git branch -M main
git remote add origin https://github.com/<your-username>/sgrt-teaching-lab.git   # create the empty public repo on github.com first
git push -u origin main
```

Then enable Pages exactly as in step A3 above (Settings → Pages → Deploy from a branch → main / root).

### Updating later

Upload (or push) a new version of a file with the same name. GitHub Pages redeploys automatically within a minute or two. If students see an old version, a hard refresh (Ctrl/Cmd + Shift + R) clears the browser cache.

### Tips for a class

- Everything runs in the browser; no data is sent anywhere and nothing is stored. Any laptop or tablet with a recent Chrome, Edge, Firefox or Safari works. Phones work but the patient simulator is more comfortable on a screen at least ~1000 px wide.
- The link also works offline afterwards if a student saves the page, because each simulator is a single file.
- To project one simulator full screen, open `teaching-cases.html` or `patient-simulator.html` directly rather than the tabbed page.
- Add `#patient` to the URL to send students straight to the second tab.

## Licence / attribution

Teaching models are synthetic and illustrative; see the "About this model" notes at the bottom of each simulator. Clinical context: AAPM TG-302 (2022).
