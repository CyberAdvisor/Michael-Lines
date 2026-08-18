# Michael Lines site contributor guide

## Project overview

This repository is the source for the static GitHub Pages site at
`michaellines.fyi`. It has no build system, package manager, or generated
source: publishable files are edited directly.

- `index.html` is the landing page.
- `about.html`, `books.html`, `blogs.html`, and `tools.html` are the other
  public pages.
- `css/style.css` is the shared stylesheet for every page.
- `images/` holds the image assets referenced by the HTML.
- `CNAME` configures the production custom domain; preserve its single-line
  format unless the domain is intentionally changing.

## Editing conventions

- Keep the site dependency-free: use plain HTML and CSS unless a request
  explicitly calls for a larger architectural change.
- Reuse the existing structure and classes. Site-wide visual changes belong in
  `css/style.css`; page-specific content belongs in its corresponding HTML
  file.
- When changing the header navigation, footer, or Statcounter snippet, update
  every HTML page so the shared UI remains consistent. Set `class="active"`
  on the navigation link for the current page only.
- Use relative paths for internal pages and assets (for example,
  `href="books.html"` and `src="images/cover-hrm.jpg"`).
- Preserve semantic markup, descriptive image `alt` text, the viewport meta
  tag, and concise page-specific title and description metadata.
- Follow the established formatting: two-space HTML/CSS indentation, lowercase
  filenames, and readable line wrapping. Do not introduce a formatter solely
  for this small static site.

## Content and assets

- Treat biographical copy, book descriptions, publication links, contact
  details, and external URLs as factual content. Do not invent or casually
  alter them; verify a source or ask when a requested change is ambiguous.
- Add new image assets under `images/` and reference those copies. Some image
  files also exist at the repository root as historical duplicates; do not add
  more root-level image copies, and do not remove existing ones without an
  explicit request.
- Use compressed, web-appropriate images and meaningful filenames. Ensure new
  images have appropriate alternative text in the page that uses them.

## Verification

There is no automated test suite. After editing:

1. Inspect the changed HTML/CSS for valid nesting, matching tags, and correct
   relative paths.
2. Review every affected page at desktop and narrow mobile widths, especially
   the responsive breakpoint at `620px`.
3. Manually check changed internal links and external URLs when network access
   is available.
4. Run `git diff --check` and review `git diff` before handing off changes.

Avoid changing unrelated copy, analytics settings, deployment configuration,
or image assets while completing a focused request.
