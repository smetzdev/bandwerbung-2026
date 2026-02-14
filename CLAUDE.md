# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Band application site for the "Schlacht um Otzenhausen 2026" heavy metal festival run by Celtic Warriors Otzenhausen. Displays ~110 bands that applied to play, sourced from a static JSON dataset. German-language, dark-mode only, accessible (screen reader support required).

## Commands

- `npm run dev` — Start dev server (localhost:4321)
- `npm run build` — Production build to `./dist/`
- `npm run preview` — Preview production build locally

No test framework is configured.

## Architecture

- **Framework:** Astro 5 (static site generation) with TypeScript (strict mode)
- **Styling:** Tailwind CSS v4 via `@tailwindcss/vite` plugin — no tailwind.config file; uses v4 inline/CSS-based configuration in `src/styles/global.css`
- **Data:** Band content lives in `src/data/bands.json` — array of objects with fields: `bandName`, `bandNameTitleCase`, `bandNameSlug`, `pdfPath`, `exampleLink`, `hometown`, `genre` (string array)
- **Components:** `src/components/Layout.astro` (HTML shell, skip-link, header/footer) and `BandCard.astro` (accessible card with article semantics, genre badges, external link button)
- **Theme:** Custom color tokens defined via `@theme` in `global.css` (surface, accent, border, text-primary/secondary). Metal Mania Google Font for headings only, system sans for body. All colors meet WCAG AAA contrast.
- **Pages:** File-based routing in `src/pages/` (currently only `index.astro`)
- **Static assets:** `public/` directory (served as-is at site root)
