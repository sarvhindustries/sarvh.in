# Admin (GitHub-only) — how to edit

This repository includes a simple admin page at `/admin/` that links to GitHub's web editor. No third-party services, OAuth apps, or CDNs are required — editing is done entirely via GitHub.

Access the admin page (after enabling GitHub Pages):
- https://sarvhindustries.github.io/sarvh.in/admin/

How to edit files (GitHub web editor flow):
1. Click an "Edit on GitHub" button on the admin page.
2. Sign in to GitHub (use your GitHub username/email and password if prompted).
3. Make your changes in the browser editor. When done click **Propose changes** to create a branch and open a Pull Request.
4. Review the PR and merge it to publish the changes to the `main` branch.

Create new pages or upload assets:
- Create a new file: https://github.com/sarvhindustries/sarvh.in/new/main?filename=pages/new-page.html
- Create assets/uploads folder: https://github.com/sarvhindustries/sarvh.in/new/main?filename=assets/uploads/README.md

Notes:
- Editing `index.html` will overwrite its contents. Keep backups if needed.
- Because this uses GitHub's UI, all editors must have a GitHub account.
- If you want me to add edit links for additional files, tell me which files and I will add them to `/admin/index.html`.

This admin approach meets your request to use only GitHub — no external services or libraries.
