# AGENTS.md — Tour Europa

**Last updated:** July 3, 2026

## Project Overview
Landing page "ΛDVENTURE EUROPA — Brutal Collection" — experiencia premium de turismo por Roma, Barcelona, París, Estambul y Madrid con ruta interactiva y presupuesto personalizado.

## Session Log

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
