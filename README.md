# Vitalis

**A clearer picture of your health, one choice at a time.**

Vitalis is a presentation site for a precision-nutrition and health-assessment prototype. It explains how personal health context, model-based risk estimates, plain-language summaries, and optional food-label insights can fit together in one experience.

**Live presentation:** [vitalis-health-assessment.vercel.app](https://vitalis-health-assessment.vercel.app/)

> **Prototype notice:** This repository contains the presentation website and a static Cloudflare Worker. It does not contain the assessment API or model services described in the product concept. The example dashboard and nutrition values are illustrative. Vitalis is not a medical device and does not diagnose or recommend treatment.

## What the site covers

- A personal health profile as context for later insights
- Separate estimates for heart health, diabetes, and weight range
- A plain-language health summary concept
- Food Lens: nutrition-label extraction and contextual food guidance
- An optional, separate research-only chest X-ray path
- Privacy and medical-use boundaries
- Responsive navigation, workflow diagrams, and architecture overview

## Project structure

```text
public/
  index.html       Presentation page and content
  styles.css       Responsive visual system and page styling
src/
  worker.js        Cloudflare Worker that serves the public assets
wrangler.jsonc     Cloudflare Workers configuration
package.json       Local development and deployment commands
```

## Run locally

Requires Node.js and npm.

```sh
npm install
npm run dev
```

Wrangler prints the local preview address when the server starts.

## Deploy

### Cloudflare Workers

Authenticate Wrangler once, then deploy from the project directory:

```sh
npx wrangler login
npm run deploy
```

The Worker serves files from `public/` through the configured `ASSETS` binding.

### Vercel

This is a static site; it has no build step. When importing the repository, use the repository root, leave the build command empty, and set the output directory to `public`.

## Privacy and safety

- The presentation preview uses made-up example values and is labeled illustrative.
- No health assessment form or backend is included in this repository.
- The product concept describes browser-local session storage for structured results; that behavior is not implemented by this presentation site.
- The concept’s optional image paths are not implemented here. If developed, images should be sent only after a user chooses analysis, and identifying details should be removed first.
- Research-model observations must remain separate from health estimates and must not guide clinical decisions.
- For health concerns, speak with a qualified healthcare professional.

## Design direction

Vitalis uses a warm paper background, deep teal and muted sage accents, editorial serif headings, and a clear sans-serif body font. The responsive layout keeps the assessment workflow and safety information readable on small screens.
