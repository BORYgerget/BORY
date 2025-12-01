# Simple PDF website (stable PDF URL)

How this works
- The site serves a PDF file named `document.pdf`.
- Any external link to the PDF should use the stable URL:
  https://<your-username>.github.io/<repo-name>/document.pdf
  (if hosted on GitHub Pages; adjust host if you use a different static host).
- To update the PDF without changing the URL, overwrite the file `document.pdf` in the same path and commit/push. Keep the filename exactly the same.

Files in this repo
- `index.html` — viewer that embeds `document.pdf` (already committed).
- `document.pdf` — your PDF file (upload this next).

Deploy on GitHub Pages
1. Place `index.html` and `document.pdf` in the repository root (they already are/will be).
2. In GitHub repository Settings → Pages:
   - Source: choose branch `main` and folder `/` (root).
   - Save. GitHub will publish the site at:
     https://BORYgerget.github.io/BORY/
3. The direct PDF URL will be:
   https://BORYgerget.github.io/BORY/document.pdf
   or
   https://BORYgerget.github.io/BORY/document2.pdf

Replace the PDF
- Using Git on your machine:
  1. Replace the file named `document.pdf` with the new PDF.
  2. `git add document.pdf`
  3. `git commit -m "Update document.pdf"`
  4. `git push`
- Using GitHub web UI:
  1. Open the repository in the browser.
  2. Click "Add file" → "Upload files".
  3. Choose the new `document.pdf` file (same name).
  4. Commit changes to `main`.

Caching notes
- The embedded viewer uses a cache-busting query string so visitors loading the page get a fresh copy quickly.
- External direct links to `document.pdf` are stable; users may see a cached version until their browser cache expires. Instruct users to hard-refresh (Ctrl/Cmd+Shift+R) if they need the newest copy immediately.
