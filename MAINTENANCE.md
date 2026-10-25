# Maintenance and release checks

The app remains a static website. No build is required for checked-in HTML, styles, images, or scripts. Node is used only to generate public content and run the browser checks.

## Blog publishing

See [content/README.md](content/README.md). Add a Markdown article and image, then run `npm run build`. The generated HTML is crawlable without JavaScript. Titles, descriptions, canonical URLs, article metadata, and the image sitemap are generated together.

The optional publishing workflow requires GitHub Pages source **GitHub Actions** and repository contents-write permission. With the existing branch-based Pages setup, merge the generated files along with your post instead. Do not enable both deployment methods deliberately for the same release.

## Verification

Install Node 22 or newer, run `npm install`, and have Google Chrome installed. Then run `npm test`. The smoke check launches headless Chrome, serves the repository locally, exercises the mind map and table, and checks flowchart editing, connections, history, persistence, JSON import, four export formats, public pages, and mobile overflow. Test artifacts are written to the OS temporary directory. The test server uses port 8123.

## Search and sharing after deployment

1. Confirm the live homepage and `/assets/logo-48.png`, `/assets/logo-512.png`, and `/assets/share-card.png` return successful responses without login. The short sharing title is “Line MindMap v2.1 — Medical Student Workspace”.
2. Submit `https://linemindmap.com/sitemap.xml` in Google Search Console and Bing Webmaster Tools. Use the relevant verified site account for other search engines such as Baidu. This code does not submit to external webmaster accounts.
3. Request a homepage recrawl in Google Search Console. Search engines and WhatsApp may retain an older title/image until their caches refresh. The repository cannot force those caches to update or guarantee a ranking.
4. The HTML site map is `/sitemap.html`, the public AI profile is `/ai/`, and machine-readable versions are `/llms.txt` and `/ai/facts.json`. Crawlers may use them, but inclusion in an AI answer is not guaranteed.
5. The owner supplied October 4, 2026 as the launch date and International Futures Trust Foundation as the funder. Add the foundation's public reference when supplied. Do not invent registration numbers, clinical approval, or accreditation.

Google Scholar is for scholarly literature. These product and study-workflow articles should use ordinary web indexing, not metadata that misrepresents them as research papers.

Primary guidance: [Google favicon requirements](https://developers.google.com/search/docs/appearance/favicon-in-search), [Google image guidance](https://developers.google.com/search/docs/appearance/google-images), [sitemap submission](https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap), [Google Scholar inclusion](https://scholar.google.com/intl/us/scholar/inclusion.html), and [Open Graph metadata](https://ogp.me/).

## Flowchart storage

Flowcharts open in a separate workspace from the existing mind map/table document. They save in the current browser under `linemindmap:flowchart:v1`; they do not currently sync to Google Drive. Download JSON for portable editable backups. PNG is rendered at up to 3× with memory limits; SVG is scalable; PDF uses a print-ready tab. Existing mind map/table save behavior is unchanged.

## Flowchart branching controls

Flowchart is available in both the first-time workspace chooser and the Add a new page chooser. It opens a separate tab and retains its existing local data. Use Tab on a selected cell or in its text editor to add a connected child. Ctrl+Enter adds a sibling sharing the current parent; for a root it adds another root. Ctrl+Tab is also handled if the browser delivers it, but most browsers reserve that shortcut for tab switching. Shift+Tab keeps normal focus navigation, and Escape leaves the text editor.

Straight branches are the default. Direction selects top-to-bottom or left-to-right and arranges the diagram. Arrange rebuilds a spaced spanning forest without removing any connections; cycles and additional cross-links are retained. Manual dragging remains available. Click an arrow to edit its label, or use Insert cell on this arrow to split it. The branching template uses generic study placeholders, not clinical instructions or reproduced study data.
