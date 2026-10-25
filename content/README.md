# Publishing a blog post

1. Add a UTF-8 Markdown file to `content/posts/`. Its filename becomes the URL slug.
2. Copy the front matter from an existing post. Set title, description, publication date (YYYY-MM-DD), image (a path under /assets/), and descriptive alt text.
3. Add a relevant image under `assets/`. Use 1200×630 pixels for a consistent article layout.
4. Write paragraphs, `##` section headings, and `-` bullet lists. Raw HTML is escaped. This lightweight renderer does not support other Markdown syntax.
5. Run `node scripts/build-content.mjs`. Commit the Markdown, image, generated blog pages, and sitemap together. The GitHub workflow below also regenerates these files when Markdown is edited on main.

Posts are public. Review factual claims and sources before merging. Publication dates are editorial metadata, not automatic claims that a crawler has indexed a page.

For automatic publishing, set repository Settings → Pages → Source to **GitHub Actions** once, and allow workflows to write repository contents. The content workflow builds the Markdown, commits the generated pages, and deploys the public site. If branch protection prevents bot commits, run the build locally and commit the generated pages in your pull request instead. The existing branch-based Pages deployment still serves the checked-in generated pages without that setup.
