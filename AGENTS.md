# Contributor Notes

This repo is the public, field-facing Vercel app for the F3 Innovate orchard stress submission.

## Mobile UX Requirement

Treat mobile as a primary use case. A field user may open this app from a phone while standing near an orchard block, so the app must not depend on desktop-only hover behavior.

Before changing the map or layout, preserve these requirements:

- The app must explain both desktop and mobile interaction. Desktop can say hover/click; mobile must say tap/drag/tap.
- Map coordinates must update from pointer movement on desktop and from tap or touch movement on mobile.
- A user must be able to tap a colored zone and immediately see whether it is problematic, the selected coordinate, the zone class, and the Google Maps route button.
- A user must also be able to click or tap an exact point of interest on the map, revise that point by clicking again, and open Google Maps to that exact coordinate even when it is not a predefined field-stop row.
- The Google Maps route must use the selected coordinate directly with `https://www.google.com/maps/dir/?api=1&destination=LAT,LON&travelmode=driving`.
- Keep selection rendering lightweight. Repeated map clicks should update the existing selected marker and details panel rather than adding many new markers or rerendering all zones.
- Touch targets should be at least roughly 44px tall for selects and route buttons.
- The map should remain tall enough to inspect on a phone, but not so tall that the user cannot reach the selected-zone details.
- Work-order rows must be readable on narrow screens without horizontal table scrolling. Use stacked card-style rows on mobile.
- Text must not overflow its container at 360px width. Long zone IDs and coordinates must wrap cleanly.
- Keep the app dependency-light: Vite, Leaflet, OpenStreetMap tiles, static GeoJSON/CSV data, and Google Maps URL links. Do not add a Google Maps API key unless there is a specific reason.

## Public Repo Standard

- Keep public docs reviewer-facing and plain.
- Keep implementation comments brief and useful.
- Do not commit local runtime folders, credentials, screenshots, drafts, or private submission material.
- Preserve this file so future coding tools inherit the mobile and routing requirements.

## Verification Gate

For mobile-affecting changes, verify all of this before deploying:

1. `npm run build` passes.
2. A 360-390px wide viewport has no horizontal page overflow.
3. The hero, quick start, translation guide, map, selected-zone panel, and top field stops are readable on mobile.
4. Tapping or dragging on the map updates the coordinate readout.
5. Tapping a zone, exact point, or top field stop exposes a route link to Google Maps.
6. The live Vercel app still returns `200` after deployment.
