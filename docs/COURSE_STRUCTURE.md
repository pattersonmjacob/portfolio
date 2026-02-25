# Course content maintenance guide

This repo is easiest to maintain when each course has its own folder under `courses/`.

## Folder + file conventions
- Use lowercase kebab-case slugs for folders (example: `sales-onboarding`).
- Keep each course's source files inside its own folder.
- Prefer one of these launch styles:
  - **Shared viewer launch:** `courseFile: "courses/<slug>/course.json"`
  - **Direct package launch:** `launchUrl: "courses/<slug>/index.html"`

## Update workflow
When you ship a new version of a course:
1. Replace files only inside that course folder.
2. Update the matching metadata in `courses.json` (title/description/type if needed).
3. Do a quick local test.
4. Commit + push.

## Suggested catalog fields
Each course in `courses.json` can include:
- `title`
- `description`
- `author`
- `type`
- `courseFile` (viewer launch)
- `launchUrl` (direct launch)

## Example entry
```json
{
  "title": "Compliance 2026",
  "description": "Annual compliance refresher.",
  "author": "Your Name",
  "type": "SCORM 2004",
  "courseFile": "courses/compliance-2026/course.json",
  "launchUrl": "courses/compliance-2026/index.html"
}
```
