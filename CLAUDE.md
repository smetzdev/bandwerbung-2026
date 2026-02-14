# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Band advertising/application site built with Astro 5 and Tailwind CSS v4. Displays a catalog of ~91 bands (primarily German metal/rock) sourced from a static JSON dataset.

## Commands

- `npm run dev` — Start dev server (localhost:4321)
- `npm run build` — Production build to `./dist/`
- `npm run preview` — Preview production build locally

No test framework is configured.

## Architecture

- **Framework:** Astro 5 (static site generation) with TypeScript (strict mode)
- **Styling:** Tailwind CSS v4 via `@tailwindcss/vite` plugin — no tailwind.config file; uses v4 inline/CSS-based configuration in `src/styles/global.css`
- **Data:** Band content lives in `src/data/bands.json` — array of objects with fields: `bandName`, `bandNameTitleCase`, `bandNameSlug`, `pdfPath`, `exampleLink`, `hometown`, `genre` (string array)
- **Pages:** File-based routing in `src/pages/` (currently only `index.astro`)
- **Static assets:** `public/` directory (served as-is at site root)
