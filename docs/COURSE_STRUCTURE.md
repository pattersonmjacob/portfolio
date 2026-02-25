# Course package workflow

Use one folder per course under `courses/` so uploads stay clean and replaceable.

## Folder naming

- Use lowercase kebab-case for each course folder.
- Example: `courses/portfolio-en-2/`

## Typical Evolve export contents

A package folder usually contains:

- `index.html`
- `course.json`
- `assets/`
- `ev-icons/`
- `manifest.json`
- `manifest.jws.json`

## Course catalog fields (`courses.json`)

Each course object can include:

- `title`
- `description`
- `author`
- `type`
- `launchUrl` (direct package launch)
- `courseFile` (shared viewer launch)

## Minimal examples

Direct launch:

```json
{
  "title": "Portfolio_en",
  "launchUrl": "courses/portfolio-en-2/index.html"
}
```

Viewer launch:

```json
{
  "title": "Portfolio_en (viewer)",
  "courseFile": "courses/portfolio-en-2/course.json"
}
```

## Publish flow

1. Upload/replace files in one course folder.
2. Update `courses.json`.
3. Run a quick local test.
4. Commit + push.
