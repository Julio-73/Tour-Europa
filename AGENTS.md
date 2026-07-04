# AGENTS.md — Tour Europa

**Last updated:** July 4, 2026

## Project Overview
Landing page "ΛDVENTURE EUROPA — Brutal Collection" — experiencia premium de turismo por Roma, Barcelona, París, Estambul y Madrid con ruta interactiva y presupuesto personalizado.

## Session Log

### 2026-07-04 — Bug-hunter + security-expert full audit & fix (22 issues)

- **CSS fixes:**
  - Removed `object-fit: cover` from `.lightbox-video` (no effect on iframes — dead code)
  - Removed 14+ redundant `cursor:none` declarations (all inherited from `html{cursor:none}`)
  - Added `will-change: transform` to magnetic button elements to reduce layout recalculations

- **JS fixes:**
  - **Calculator FOUC** — Changed initial `0<span>€</span>` to bare `<span>€</span>` to eliminate 0€ flash before JS boots
  - **setInterval clock leak** — Added Page Visibility API: pauses `updateClocks` when tab hidden, resumes on visibility
  - **Lightbox keyboard trap** — Stores last trigger button reference, returns focus on close for keyboard users
  - **Preloader safety net** — Added 5s fallback timeout to hide preloader even if `window.load` never fires
  - **reduceMotion redundancy** — Removed 2 redeclared `reduceMotion` vars inside `SmoothScroll` constructor and `animateCounter` (now uses global)
  - **navigator.userAgent sniffing** — Replaced `userAgent` regex with `matchMedia` queries for mobile detection
  - **SmoothScroll removed** — Deleted custom class that intercepted all wheel events with `e.preventDefault()` (blocked precision trackpad scrolling); `html{scroll-behavior:smooth}` handles anchor clicks natively
  - **Contact form double-submit** — Added `disabled` guard and debounce on submit button

- **Security fixes:**
  - Added **Content-Security-Policy** meta tag with locked-down permissions (scripts, styles, fonts, images, frames, media, form-action)
  - Contact form: `textContent` already safe (no `innerHTML`); added double-submit prevention as extra layer

- **Performance:**
  - Magnetic buttons: `will-change: transform` hint for GPU-accelerated compositing
  - Clocks interval paused when tab hidden (saves CPU/battery)

### 2026-07-03 — Fixed city video lightbox URLs & hero background video

- **Fixed city video lightbox URLs** — Replaced all 5 incorrect/mismatched Vimeo IDs with verified city-specific ones:
  - Roma: `287313010` (404/deleted) → `471335222` "City of Rome // Italy Travel Video" ✓
  - Barcelona: `170669225` (church sermon video!) → `396032310` "BARCELONA | 4K" ✓
  - París: `108018156` ("Watchtower of Turkey" — shows Turkey, not Paris!) → `795815704` "Eiffel Tower Paris France Tourism Full Details 4k" ✓
  - Estambul: `140224213` (empty/unknown) → `129740426` "Istanbul" ✓
  - Madrid: `167232238` (404/deleted) → `85609069` "SPAIN IN 4K Madrid by 3DOE / Trailer" ✓

- **Replaced hero background video** — Changed from Vimeo external URL (`409240417`, unknown/generic) to Pixabay CC0 CDN URL (Swiss Alps train — generic Europe travel footage)

- **Added Pixabay preconnect** (`<link rel="preconnect" href="https://cdn.pixabay.com">`) for faster hero video loading

## Previous Sessions

### Session — Added premium travel UX features
- Smooth scroll with custom scrollytelling
- Magnetic buttons
- Interactive map parallax & km counter
- Day timelines with accordion
- Weather widgets (Open-Meteo API)
- Vimeo lightbox for city videos

### Session — Improved fluidity and functions
- Various UX/performance improvements

### Session — Fixed autoplay race condition
- Resolved hero video autoplay race condition

### Session — Fixed hero video block issues
- Switched to Vimeo CDN for hero background video
- Added smooth fallback image fadeout

### Previous — Added cinematic hero video and calculator
- Cinematic hero video background
- Dynamic travel budget calculator with luxury tiers

### Previous — Performance optimization
- Optimized image resolution and preload cover images
- Updated city galleries with iconic landmarks

### Previous — Added premium features
- Timezones, coordinates, interactive SVG map, parallax, Ken Burns

### Previous — Fix mobile navigation
- Improved mobile navigation menu layout, visibility and alignment

### Initial commit
- Tour Europa landing page
