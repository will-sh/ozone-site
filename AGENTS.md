## Cursor Cloud specific instructions

- This branch is the rendered Apache Ozone website (`asf-site`), not the Hugo source tree. The root `README.md` explains that most site content is generated elsewhere; only `docs/` is intended for direct edits on this branch.
- There are no repository-local dependency manifests or setup scripts on this branch. The Cursor Cloud startup dependency refresh is intentionally a no-op.
- For local development checks, serve the repository as static files (for example with `python3 -m http.server 8000 --bind 127.0.0.1`) and exercise the website over HTTP. Root pages use an HTML `<base href="https://ozone.apache.org/">`, so relative assets on those pages resolve from the site root when validating links.
- Standard validation for this branch should focus on the rendered artifact surface: HTTP smoke tests for key pages, local asset checks for touched pages, and confirming the generated HTML/CSS/JS assets are present. There is no source build command in this branch.
