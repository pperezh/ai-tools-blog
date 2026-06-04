# Walkthrough: AI Tools Subdomain & Repository Separation

We have successfully initialized the standalone repository for your AI Tools blog, configured the theme, copied the content and assets, established a publishing automation workflow, and linked the main site to the new subdomain.

Here is a summary of the changes and instructions for the remaining domain settings.

---

## 1. Summary of Changes

### Standalone Blog Repository: `/Users/pperezh/agy-ai-tools-blog/`
* **Initialized Hugo & Git**: Set up a clean Hugo project.
* **Theme submodule**: Added the `blowfish` theme as a submodule locked to the same stable commit hash (`3a9016a6d93f6d498ab5fc3b0aa7d51869962f25`) as the main site to avoid version issues.
* **Migrated content**: Copied `content/ai-tools/*` into the root `content/` folder of the new repository.
* **Migrated assets**: Copied logo and bio image assets into the new repo's `assets/img/`.
* **Configured hugo.toml**: 
  * Pointed `baseURL` to `https://ai-tools.pperezh.com/`
  * Added navigation headers with links pointing back to your main site `https://pperezh.github.io/`.
* **Automated Publishing (`deploy.yml`)**:
  * Set up GitHub Actions to build and deploy to GitHub Pages.
  * Added a daily cron trigger (`0 0 * * *`) that rebuilds the site every day. This enables scheduling future-dated posts (e.g., setting `date: 2026-06-10` in frontmatter will keep a post hidden until that date, when the daily build will automatically publish it).
* **Archetype Layout (`default.md`)**: Configured a lightweight frontmatter template matching the style of your existing articles.

### Main Site Repository: `/Users/pperezh/agy-hugo-website/`
* **Updated hugo.toml**: Updated all relative links `/ai-tools/` and `/es/ai-tools/` in menus and author sections to absolute subdomain URLs:
  * `https://ai-tools.pperezh.com/`
  * `https://ai-tools.pperezh.com/es/`
* **Deferred content deletion**: Left the original `content/ai-tools` folder intact in the main repo per request.

---

## 2. Verification

We verified the local builds of both repositories:
* **Main Website**: Build succeeded cleanly with no errors.
* **AI Tools Blog**: Build succeeded cleanly with the custom configurations.

---

## 3. Deployment & DNS Configuration Steps

To go live with `https://ai-tools.pperezh.com/`, follow these two steps:

### Step A: Configure DNS in Porkbun
1. Log into your [Porkbun Dashboard](https://porkbun.com).
2. Go to your domain `pperezh.com` and open the **DNS Settings**.
3. Create a new record with the following values:
   * **Type**: `CNAME`
   * **Host/Subdomain**: `ai-tools`
   * **Answer/Value**: `pperezh.github.io`
   * **TTL**: `600` (or default)
4. Save the record.

### Step B: Configure GitHub Pages for the Blog Repository
Once you push your new repository to a public GitHub repository (e.g., `github.com/pperezh/ai-tools-blog`):
1. In the repository on GitHub, go to **Settings** -> **Pages**.
2. Under **Build and deployment**:
   * **Source**: Choose **GitHub Actions**. (The `deploy.yml` workflow will automatically run and publish it).
3. Under **Custom domain**:
   * Type in **`ai-tools.pperezh.com`**.
   * Click **Save**.
4. Check **Enforce HTTPS** (this may take a few minutes to become available while GitHub provisions the SSL certificate).
