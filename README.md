# VulGen Workshop Website — Editor Guide

This is the website for the **VulGen: International Workshop on Vulnerabilities in Generative Systems for Information Retrieval** at ACM SIGIR 2026. It is built with [Hugo](https://gohugo.io/) and deployed automatically to GitHub Pages on every push to `main`.

**Live site:** https://vulgen-workshop.github.io/SIGIR2026/

---

## Requesting Access

Contact any of the 2026 organizers to be added as a collaborator on the GitHub repository.

---

## Making Content Edits

All site content lives in the `content/` folder as Markdown files:

| File | Page |
|---|---|
| `content/_index.md` | Home |
| `content/about/_index.md` | About |
| `content/dates/_index.md` | Important Dates |
| `content/submission/_index.md` | Call for Submissions |
| `content/schedule/_index.md` | Schedule |
| `content/organizers/_index.md` | Organizers |

Edit the relevant `.md` file and push to `main` — the site deploys automatically within a minute or two.

Organizer photos go in `static/images/` and are referenced as `{{<img src="images/filename.jpg" ...>}}`.

---

## Updating Structure or Styling

| What | Where |
|---|---|
| Site title, nav, footer, config | `hugo.yaml` |
| Brand colours | `assets/sass/_custom.scss` |
| Page layout/templates | `themes/zen/` (Hugo Zen theme — see its [README](https://github.com/frjo/hugo-theme-zen)) |
| Custom shortcodes | `layouts/shortcodes/` |
| Deployment workflow | `.github/workflows/hugo.yaml` |

To add a new page, create `content/<page-name>/_index.md` with a `title` and `weight` (controls nav order) in the front matter.

---

## First-Time Repository Setup (GitHub Pages)

If you forked or transferred this repository and the site isn't deploying, you need to enable GitHub Pages once:

1. Go to **Settings → Pages** in the repository on GitHub.
2. Under **"Build and deployment" → "Source"**, select **"GitHub Actions"**.
3. Click **Save**.
4. Re-run any failed workflow under the **Actions** tab.

This is a one-time step — deployments will succeed automatically from then on.

---

## Local Preview

```bash
git clone --recurse-submodules https://github.com/vulgen-workshop/SIGIR2026
cd SIGIR2026
hugo server
```

Then open http://localhost:1313/SIGIR2026/
