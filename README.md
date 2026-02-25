# LMS Portfolio (GitHub Pages Course Launcher)

This repo is a **simple landing page + course catalog**.

- Add your exported course package files to a folder.
- Add one entry to `courses.json`.
- Push to GitHub.
- The course appears on the landing page.

## Live URL
`https://pattersonmjacob.github.io/portfolio`

## Recommended folder layout

```text
portfolio/
├─ index.html
├─ courses.json
├─ course-viewer.html
├─ courses/
│  ├─ portfolio-en-2/
│  │  ├─ index.html
│  │  ├─ course.json
│  │  ├─ assets/
│  │  ├─ ev-icons/
│  │  ├─ manifest.json
│  │  └─ manifest.jws.json
│  └─ another-course/
│     ├─ index.html
│     └─ assets/
└─ docs/
   └─ COURSE_STRUCTURE.md
```

## `courses.json` examples

### 1) Launch package directly (Evolve export with its own `index.html`)

```json
{
  "title": "Portfolio_en (Direct)",
  "description": "Standalone package export from Evolve.",
  "author": "Jacob Patterson",
  "type": "Web package",
  "launchUrl": "courses/portfolio-en-2/index.html"
}
```

### 2) Launch through shared viewer (using `course.json`)

```json
{
  "title": "Portfolio Course (Viewer)",
  "description": "Uses the shared course viewer shell.",
  "author": "Jacob Patterson",
  "type": "SCORM/Web",
  "courseFile": "courses/portfolio-en-2/course.json"
}
```

## Add a new course in 3 steps

1. Upload your exported package into `courses/<slug>/`.
2. Add a matching object in `courses.json`.
3. Commit + push to `main`.

GitHub Pages deploys automatically from the workflow in `.github/workflows/pages.yml`.

## Local test

```bash
python3 -m http.server 8000
# open http://localhost:8000
```
