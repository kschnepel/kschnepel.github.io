# Kevin Schnepel's academic website

Live at **https://kschnepel.github.io**. GitHub Pages serves the `master` branch of
`github.com/kschnepel/kschnepel.github.io` as-is. There is no build step and no Jekyll
(`.nojekyll` turns it off). Whatever is in this folder is the site.

## Where things live

```
~/Dropbox/mywebsite/
├── kschnepel.github.io/   ← this folder: the website (everything here is PUBLIC)
└── cv/                    ← CV source: cv.tex + res.cls (compiled on Overleaf)
```

The CV source stays outside the site folder on purpose. It contains commented-out
material that shouldn't be published. Only the compiled PDF goes into `files/`.

`cv.tex` uses latin9 input encoding, so write plain ASCII in it: `--` for a dash and
`` ``…'' `` for quotes. When papers change, update **both** `cv.tex` and `index.html` so they
stay in sync. Verify citations against Crossref (`https://api.crossref.org/works/<DOI>`).

## Files

| File / folder | What it is |
|---|---|
| `index.html` | **All the content.** One page with these sections in order: header, About, Research (Publications, Working Papers, Work in Progress, Other Writing), Policy & Media, CV, footer. Each section starts with a `===== N. NAME =====` comment. |
| `style.css` | The look. Colors are defined once at the top, and dark mode swaps them. |
| `files/` | PDFs: CV and paper drafts. **Never rename or delete these.** Other sites, old CVs, and Google Scholar link to them. Add new files next to the old ones. |
| `images/headshot.jpg` | The photo, resized to 640px. `websitepic2.png` is the full-size original. |
| `404.html` | Sends old URLs from the pre-2026 site (`/research/`, `/cv/`, single paper pages) to the right spot on the new page. |

## Common updates

**Add a paper.** Copy an existing `<li class="paper">` block in the right list and edit it.
Lists run newest first. Each block has:
- `id`: a short, unique slug like `heroin-supply`. It makes the `#heroin-supply` link work, so don't change it once the paper is live.
- `paper-title`: the title, linked to the best version (journal DOI if published, else NBER or the PDF).
- `paper-meta`: "with Coauthor A and Coauthor B · <cite>Journal</cite>, Year". Use "forthcoming" or "Revisions requested, <cite>Journal</cite>" when that applies. No page numbers; the full citation is on the CV.
- `links`: buttons such as PDF, Journal, NBER. The "Abstract" button is added automatically when there's an abstract.
- `abstract` (optional): `<div class="abstract"><p>…</p></div>`
- `media` (optional): `In the media: <a>Outlet</a>, …`

**A working paper gets accepted.** Move its block from Working Papers to the top of
Publications. Update `paper-meta` and add a "Journal" link. Keep the `id`.

**New CV.** Kevin compiles `../cv/cv.tex` on Overleaf and saves the PDF in `../cv/`.
Copy it in as `files/Schnepel_CV_YYYY.pdf` and keep the old one. Then
update the **two** links that point to it in `index.html`: the header "CV (PDF)" chip
and the "Download full CV" button in the CV section.

**Every edit.** Update "Last updated Month YYYY" in the footer.

## Preview locally

```bash
cd ~/Dropbox/mywebsite/kschnepel.github.io && python3 -m http.server 8000
```

Then open http://localhost:8000. Opening `index.html` directly also works, except for `404.html`.

## Publish

```bash
git add -A && git commit -m "Describe the change" && git push origin master
```

The live site updates about a minute after the push. Always show Kevin a preview first,
and push only after he approves.

## Conventions

- Plain HTML only. No frameworks, build tools, or new JavaScript dependencies.
- Use typographic quotes and dashes (’ “ ” –).
- The old Jekyll/AcademicPages site is in git history (before the 2026 redesign commit) if anything needs recovering.
