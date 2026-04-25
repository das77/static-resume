# static-resume

This repository is a static website project for the Full Stack Engineering program

## Rationale

### HTML Structure

The HTML follows a semantic, document-outine structure using native HTML5 elements:

- **`<header>`** — Contains the site title, profile image, and navigation. Wraps branding and nav in a logical header block.
- **`<nav>`** — Dedicated navigation element with `aria-label="Primary navigation"` for screen readers.
- **`<main>`** — Identifies the primary content area using the `role="main"` attribute for backward accessibility support.
- **`<section>`** — Groups related content (About, Skills, Projects) with heading elements (`<h2>`) that provide document structure.
- **`<article>`** — Used for self-contained content blocks like individual skills or projects.
- **`<footer>`** — Contains copyright information, providing a clear page end marker.

Each page (index.html, projects.html, contact.html) follows this same template pattern for consistency and maintainability.

### CSS Layout Approach

The project uses an external stylesheet (`css/style.css`) for separation of concerns:

- **External CSS** — Keeps HTML clean and enables caching across pages.
- **Grid-based form layout** — The contact form uses `display: grid` with a `max-width` constraint to keep input boxes aligned while preventing excessive width on large screens.
- **Inline styles** — Used sparingly for page-specific tweaks (e.g., image sizing, form alignment).

### Accessibility Considerations

- **`lang="en"`** — Declares the language on the `<html>` element for screen readers.
- **`aria-label`** — Added to navigation and form elements to provide context.
- **Semantic elements** — Using `<nav>`, `<main>`, `<section>` helps assistive technologies navigate the page structure.
- **Form labels** — Every `<input>` and `<textarea>` has an associated `<label>` with a `for` attribute linking to the input's `id`.
- **Alt text** — Profile image includes descriptive `alt` text.

### Responsive Design Strategy

The site uses a **desktop-first** approach for this initial implementation:

- **Viewport meta tag** — `width=device-width, initial-scale=1.0` ensures proper scaling on mobile devices.
- **Image sizing** — The `sizes` attribute on the profile image provides hints to the browser for responsive image loading:
  - `(min-width: 1440px) 33vw` — 33% of viewport at large screens
  - `(min-width: 1024px) 50vw` — 50% at medium screens
  - `100vw` — Full width on mobile
- **Fluid widths** — Form inputs use `width: 100%` within a constrained container to adapt to screen size while maintaining readability.

The desktop-first approach was chosen because the resume is primarily intended for desktop viewing (e.g., LinkedIn profile link), with mobile serving as a fallback. A mobile-first refactor could be considered for future iterations if mobile traffic increases.
