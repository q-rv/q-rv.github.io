# Design — q-rv

## 1. Introduction
`q-rv` is the personal landing page and web presence for rv. Its architectural philosophy is "Single-File Static Perfection": a zero-dependency, self-contained single HTML document optimized for instant loading, responsive rendering across all screen sizes, and seamless dark/light theme switching.

## 2. Tech Stack
- **Markup & Styling**: HTML5, CSS3 (CSS Custom Properties / Variables)
- **Scripting**: Vanilla JavaScript (ES6, inline self-executing function)
- **Typography**: Google Fonts (`Dancing Script`), Apple System Font stack
- **Hosting/Platform**: Static Web (GitHub Pages / CDN)

## 3. Technical Architecture
- **Single-File Architecture**: HTML markup, CSS stylesheet, and JavaScript logic are co-located in `index.html` to eliminate round-trip HTTP requests and asset resolution overhead.
- **Theme Engine**: Driven by CSS variables (`--bg`, `--fg`, `--muted`) toggled via `data-theme` attribute on the root `<html>` element.
- **System Theme Auto-Detection**: Uses `window.matchMedia('(prefers-color-scheme: light)')` to set initial theme, overriding with user choice cached in `localStorage`.

## 4. File Structure
```text
q-rv/
├── index.html       # Self-contained single-page web document
└── DESIGN.md        # Architecture specification
```

## 5. Implementation Details
- **Palette Tokens**:
  - Dark Navy: `#0d1b2a`
  - Off-White: `#f5f3ee`
  - Denim Blue: `#3b5b8c`
  - Accent Red: `#d72638`
- **Fluid Typography**: Uses CSS `clamp()` (`clamp(5rem, 24vw, 15rem)`) to dynamically scale banner lettering across mobile, tablet, and desktop viewports without media queries.
- **Inline SVG Icons**: Sun and moon theme toggle icons embedded as vector SVG paths to avoid external image requests.

## 6. Build & Run
- No build process required.
- Serve via any local HTTP server (e.g., `python3 -m http.server`) or open `index.html` directly in any web browser.

## 7. Tooling & Dependencies
- Zero external runtime or build dependencies.
- Relies only on Google Fonts CDN for the cursive display typeface.

## 8. Security & Standards
- Strict HTML5 compliance.
- No third-party analytics, tracking scripts, cookies, or external JavaScript libraries.
