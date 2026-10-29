# Copilot instructions

Project context Copilot should apply to every session in this repository.

## Stack

- Framework: Astro (static output).
- Language: TypeScript.
- Styling: plain CSS in the base layout.

## Conventions

- Keep components small and focused.
- Prefer semantic HTML and accessible markup.
- Do not close, or add closing keywords for, the exercise walkthrough issue (issue #1) in any pull request. The exercise's GitHub Actions workflows manage that issue. When you open a pull request for app work, link only the specific app work-item issue you are implementing.

## Persistence and hydration rules

1. **Persistence:** store bookmarks in the browser with `localStorage` (for example under a single `bookmarks` key as a JSON array of `{ url, slug }`). There is no backend or URL-shortener service; the short slug is generated locally. Always wrap `localStorage` reads/writes in `try/catch` and fall back to an empty list if the data is missing or invalid.
2. **Hydration:** `localStorage` and other browser APIs (`window`, `document`) may only be used in client-side code. Put that logic in an interactive island rendered with the `client:load` directive (or in a `<script>` that runs in the browser), never in Astro component frontmatter, so the static build/SSR never touches browser APIs.
