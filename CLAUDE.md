# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## How to run

Open `index.html` directly in a browser — no build step, no dependencies, no server required.

## Architecture

This is a single-file static web app (`index.html`). All HTML, CSS, and JavaScript live in one file with no external dependencies beyond Google Fonts.

**Key constants and data:**
- `ACTIVITIES` — the fixed array of everyday activities, each with an emoji, name, and duration in hours
- `COLORS` — pill background colors cycled by index
- `DEFAULT_SALARY` — fallback when the input is empty or invalid (43000)
- `MASSACHUSETTS_RATE` — flat 5% state tax
- `STANDARD_DEDUCTION` / `FED_BRACKETS` — 2025 federal tax brackets for a single filer with the standard deduction; federal tax is computed progressively then subtracted from gross salary alongside the MA flat tax

**Earnings model:**
- Hourly rate = `salary / 8760` (all 8,760 hours in a year, not just work hours — this is intentional)
- After-tax rate applies the Massachusetts flat withholding rate
- Federal tax uses 2025 progressive brackets for a single filer with the $15,000 standard deduction; no credits or itemized deductions

**Rendering flow:**
1. `init()` picks 4 random activities, renders pills, and attaches event listeners
2. Salary `input` events call `updateEarnings()`, which patches `.pill-earning` elements in place without re-rendering pills
3. The "Show me more" button calls `pickRandom4()` + `renderPills()` to do a full re-render with new activities

## Adding or editing activities

Add entries to the `ACTIVITIES` array in the `<script>` block. Each entry needs `emoji` (string), `name` (string), and `hours` (number).
