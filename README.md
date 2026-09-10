# Pangasinan Heritage Digital Showcase

Academic prototype for Activity 1.1 using Vue + Nuxt 3 and Brad Frost's Atomic Design methodology.

## Requirements
- Node.js 22.x or newer (even-numbered Node release recommended)
- npm

## Run locally
```bash
npm install
npm run dev
```

Open http://localhost:3000.

## Static build
```bash
npm run generate
```

The generated static site is placed in `.output/public`.

## Atomic Design structure
- `components/atoms/` — Button, Typography, Color Tokens, Icon, Image
- `components/molecules/` — Heritage Card, Search Form, Navigation Item
- `components/organisms/` — Heritage Grid, Header Navigation
