# Admin (GitHub-only) — setup instructions

This adds a simple GitHub-hosted admin UI at `/admin` using Netlify CMS. The UI lives inside this repository and uses GitHub as the backend (via a GitHub OAuth App). Changes are created as pull requests (editorial workflow) so they can be reviewed before merging.

Files added:
- `admin/index.html` — admin UI loader (Netlify CMS)
- `admin/config.yml` — CMS configuration (repo, branch, media folder, collections)

Steps to finish setup (you must do these in your GitHub account):

1. Enable GitHub Pages for this repository
   - Settings → Pages → Build and deployment → Branch: `main` / (root)
   - Save. The site will be available at: `https://sarvhindustries.github.io/sarvh.in/`
   - The admin will be reachable at: `https://sarvhindustries.github.io/sarvh.in/admin/`

2. Create a GitHub OAuth App (to allow the admin to authenticate with GitHub)
   - In GitHub, go to Settings → Developer settings → OAuth Apps → New OAuth App
   - Application name: Sarvh.in CMS (or any name)
   - Homepage URL: `https://sarvhindustries.github.io/sarvh.in/`
   - Authorization callback URL: `https://sarvhindustries.github.io/sarvh.in/admin/`
   - Create the app and copy the **Client ID** (and **Client Secret**). Keep the secret private — do not commit it to the repo.

3. Configure the CMS client_id
   - Open `admin/config.yml` and replace `GITHUB_OAUTH_CLIENT_ID` with the Client ID from the OAuth App.
   - If you prefer the CMS to use direct commits (not PRs), remove or change `publish_mode`.

4. Optional: host the Netlify CMS script locally (all assets from GitHub)
   - By default `admin/index.html` loads Netlify CMS from a CDN. If you want everything to be served from GitHub only, download the Netlify CMS bundle and commit it to `admin/netlify-cms.js`, then replace the script tag in `admin/index.html` to load that local file.

5. Test the admin
   - Visit `https://sarvhindustries.github.io/sarvh.in/admin/` and sign in via GitHub (authorize the OAuth App when prompted).
   - Create an edit for the Home page. A pull request should be opened (editorial workflow). Review and merge the PR to publish changes.

Important security notes
- Do not commit your OAuth Client Secret to the repo. Only the Client ID is placed in `admin/config.yml`.
- Editorial workflow creates PRs — reviewers can inspect changes before merging.

If you want, I can:
- Replace the CDN script with a local copy committed to `admin/netlify-cms.js` so all admin assets are served from GitHub Pages only.
- Add other pages (about.html, contact.html) to `collections` so they are editable from the UI.
- Open a PR instead of committing directly to `main` (let me know if you prefer that flow).

---
