# Writing Archive

A living archive of long-form writing by Payal Gusain, organic growth and content strategist for SaaS, AI and VC firms.

**→ [pgwrites.github.io/writing-archive](https://pgwrites.github.io/writing-archive/)**

---

## How it works

The whole site is one `index.html` on GitHub Pages, with no build step and no CMS. The list of pieces lives in a Google Sheet that's published to the web as CSV. The page fetches that CSV on load and builds the cards and the Topic and Format filters from it.

If the published CSV can't be reached, the page tries the sheet's `gviz` endpoint, then a public CORS proxy (allorigins.win). If all three fail, it shows demo content.

## Maintaining

- **Adding a piece:** add a row to the Google Sheet, not this repo. The page loads the sheet's published CSV. Only `Description` is shown on cards (not `Thumbnail`), and only the year of `Date` is used.
- **Hosting a PDF:** put it in `files/`, add a sheet row linking to `https://pgwrites.github.io/writing-archive/files/<filename>`, and add the same URL to `sitemap.xml`.
- **Demo cards on the live site** mean the sheet couldn't be loaded. Check that it's still published to the web.
- Don't delete `google*.html`; it's the Search Console verification.
