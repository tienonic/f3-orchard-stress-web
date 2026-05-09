# F3 Orchard Stress Web App

This public repo contains the field-facing Vercel app for the F3 Innovate orchard stress submission. The app converts mapped orchard stress zones into inspection targets with coordinates and Google Maps routing.

Reviewers should open the live app first.

Live app: https://f3-orchard-stress-web.vercel.app

Public source: https://github.com/tienonic/f3-orchard-stress-web

Final report guide: `docs/final-report-guide.md`

## What It Does

- Starts reviewers on the clearest orchard-scale example before the larger public-boundary maps.
- Select a public orchard site.
- Read map coordinates from hover, tap, drag, or click.
- Click a colored stress zone to see whether it is a scouting priority.
- Click any exact point of interest to route to that coordinate.
- Open the selected point in Google Maps for field navigation.

The app is for inspection prioritization, not diagnosis. It helps a scout decide where to look first, then the field visit determines the cause.

## Local Development

```powershell
npm install
npm run dev
```

## Build

```powershell
npm run build
```

## Deploy

Run from this folder:

```powershell
vercel deploy
vercel deploy --prod
```

The app uses Leaflet with OpenStreetMap tiles for the map display and Google Maps direction URLs for navigation. No Google Maps API key is required.
