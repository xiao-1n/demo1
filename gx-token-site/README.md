# GX Token Site

A Vite + React + TypeScript project styled with Tailwind CSS. The site targets desktop browsers and uses a dark sci-fi palette.

## Setup

Install dependencies:

```bash
npm install
```

## Development

Start the dev server with hot reload:

```bash
npm run dev
```

## Production Build

Create a production bundle and copy it to `docs/` for GitHub Pages:

```bash
npm run build:prod
```

## Deploy to GitHub Pages

Example GitHub Actions workflow:

```yaml
name: Deploy
on:
  push:
    branches: [main]

jobs:
  gh-pages:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 18
      - run: npm ci
      - run: npm run build:prod
      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          publish_dir: docs
```

The generated site will be served from the `docs/` directory on the `gh-pages` branch.
