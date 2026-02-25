# LMS Portfolio

Welcome to my Learning Management System Portfolio. This repository is set up as a **landing page + course catalog** so you can keep adding/updating courses over time.

## 🔗 View Live
Visit: `https://pattersonmjacob.github.io/portfolio` once GitHub Pages is enabled or the deployment workflow has run.

> **Automatic deployment**
> A GitHub Actions workflow (`.github/workflows/pages.yml`) publishes this repo to GitHub Pages whenever you push to `main`.

## Recommended repo structure for ongoing updates
Use one folder per course so updates are isolated and easier to maintain:

```text
portfolio/
├─ index.html                  # landing page (course cards)
├─ courses.json                # catalog used by landing page
├─ course-viewer.html          # shared viewer for Evo-style course.json files
├─ courses/
│  ├─ sales-onboarding/
│  │  ├─ course.json
│  │  └─ assets/... (optional)
│  ├─ compliance-2026/
│  │  ├─ course.json
│  │  └─ assets/... (optional)
│  └─ leadership-basics/
│     └─ index.html            # optional direct package launch
└─ docs/
   └─ COURSE_STRUCTURE.md      # maintenance workflow
```

## How to add or update courses
1. Create/update the course in its own folder, for example:
   - `courses/sales-onboarding/course.json`
2. Add/update the matching entry in `courses.json`.
3. Commit and push to `main`.

### `courses.json` patterns
Use `courseFile` when the course should open in the shared viewer.

```json
{
  "title": "Sales Onboarding",
  "description": "Interactive onboarding for the sales team.",
  "author": "Your Name",
  "type": "SCORM 1.2",
  "courseFile": "courses/sales-onboarding/course.json"
}
```

Use `launchUrl` when you want to open a standalone package directly.

```json
{
  "title": "Leadership Basics (Standalone)",
  "description": "Standalone exported package.",
  "author": "Your Name",
  "type": "Web Package",
  "launchUrl": "courses/leadership-basics/index.html"
}
```

You can include **both** `courseFile` and `launchUrl` on one course if you want both actions available.

## GitHub Pages deployment troubleshooting
If the deployment workflow fails with errors like **permission denied to github-actions[bot]** or missing `gh-pages` branch:

1. Confirm the workflow has write permissions (`contents: write`) — already configured in `.github/workflows/pages.yml`.
2. In GitHub repository settings, ensure Actions has permission to create/update branches.
3. Re-run the **Deploy GitHub Pages** workflow (or push a new commit).

This workflow deploys from `main` to `gh-pages` and can create/reset `gh-pages` automatically using `force_orphan: true`.

## 🛠️ Develop locally
```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## More detail
See `docs/COURSE_STRUCTURE.md` for a practical update checklist and naming conventions.
