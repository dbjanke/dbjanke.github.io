# AGENTS.md

## Agent Guidance

This repo is a **Jekyll site published through GitHub Pages**. Favor a **layout-driven system** with clear, predictable structure. Preserve these boundaries:

- **Layouts** define page-level structure.
- **Includes** hold small, reusable presentation fragments.
- **Content** lives in pages, posts, and collections with clear front matter.
- **Data** belongs in `_data` when it is reused or structured.
- **Config** belongs in `_config.yml` and should stay explicit and minimal.
- **Assets** should remain simple, organized, and easy to trace.

Prefer familiar Jekyll patterns over custom systems. Keep Liquid straightforward. Avoid clever abstractions that make templates harder to read, debug, or extend.

Simplicity means **few concepts, clear relationships, and low maintenance cost**. Prefer simple code over flexible-but-complex approaches. Optimize for readability, compatibility, and long-term ease of editing.

---

## Workflow (Default Operating Mode)

Make the **smallest change** that solves the problem.

Do not refactor unrelated files. If you notice issues outside scope, call them out but do not fix them unless asked.

Prefer existing patterns over introducing new ones. Keep diffs reviewable. Avoid drive-by renames, formatting-only edits, or file reorganization unless the task requires them.

Ask before changes that:

- materially change site structure or navigation
- significantly alter visual design or page behavior
- introduce new dependencies, plugins, or build assumptions
- expand scope beyond the requested page, layout, or theme task

Because this site is built by **GitHub Pages**, maintain **strict GitHub Pages compatibility**. Do not rely on unsupported plugins, custom build steps, or local-only behavior.

---

## Project Structure Boundaries

**Boundaries are intentional. Do not blur content, layout, and configuration.**

### Layouts

Layouts should define the overall page skeleton and shared structure. Keep them clean and predictable. A layout should make it obvious how a page is assembled.

Do not overload layouts with page-specific logic that belongs in content or front matter.

### Includes

Includes should be small, focused, and reusable. Use them for repeated UI fragments, not as a substitute for page structure.

Avoid building a complex component system in Liquid. Pass only the data needed for the include to render clearly.

### Content

Pages, posts, and collection items should stay content-first. Front matter should be explicit and limited to fields the site actually uses.

Do not bury content structure inside complex Liquid conditionals when a clearer layout or include would solve the problem.

### Data

Use `_data` for structured information that appears in multiple places or should be maintained centrally.

Do not move one-off content into data files without a clear reuse benefit.

### Config

Keep `_config.yml` explicit, minimal, and easy to understand. Prefer clear settings over hidden behavior.

Fail fast on invalid or missing configuration where possible. Do not introduce unnecessary config surface area.

### Assets

Keep CSS, images, and other assets organized and lightweight. Prefer simple, maintainable styling over heavy frameworks or excessive client-side behavior.

---

## Compatibility Rules

This project must remain compatible with **GitHub Pages’ supported Jekyll environment**.

Prefer built-in Jekyll features and widely used, low-risk patterns. Do not introduce unsupported plugins, Ruby extensions, or custom site generation steps. Treat local-only solutions as unacceptable unless explicitly requested and clearly isolated from production publishing.

When recommending plugins, prefer doing without them unless they provide clear value and are compatible with GitHub Pages.

---

## Design and UX Principles

The design should feel **clean, calm, and accessible**. Prefer clarity over novelty.

Use visual changes only when they improve comprehension, usability, hierarchy, or accessibility. Avoid decorative complexity, heavy motion, and default framework aesthetics that do not fit the site.

Favor semantic HTML, good heading structure, keyboard-friendly interactions, sufficient color contrast, and responsive layouts that work well across common screen sizes.

Keep pages lightweight. Avoid unnecessary JavaScript. Prefer HTML and CSS solutions when they are sufficient.

---

## Liquid and Template Principles

Keep Liquid logic simple, explicit, and easy to follow. Prefer straightforward conditionals and loops over deeply nested or highly abstract template logic.

Do not create indirection unless it clearly reduces duplication without making the site harder to understand.

When choosing between a slightly repetitive solution and a clever one, usually choose the more readable option.

---

## CSS and Styling

Prefer simple, well-organized CSS. Keep selectors understandable and avoid unnecessary specificity.

Make style changes in the most local, predictable place that fits the existing structure. Do not introduce large styling systems or frameworks unless explicitly requested.

Preserve consistency in spacing, typography, color usage, and responsive behavior across templates.

---

## Quality Checks

For every meaningful change, validate by checking that the site still builds cleanly in the expected GitHub Pages-compatible setup and that the rendered output matches the requested behavior.

Watch for broken layouts, invalid links, missing assets, malformed front matter, accessibility regressions, and unintended visual changes.

---

## Change Management

Prefer stable, incremental improvements over sweeping redesigns.

Do not change URLs, permalinks, file structure, naming conventions, or front matter schemas unless the task requires it.

When a better pattern is obvious but outside the requested scope, note it briefly instead of silently expanding the work.

---

## Decision Heuristics

When in doubt:

- prefer **GitHub Pages compatibility** over flexibility
- prefer **layouts** over complex include chains
- prefer **includes** over duplicated markup when reuse is real
- prefer **data files** only when content is reused or structured
- prefer **simple Liquid** over abstraction
- prefer **semantic HTML and accessible CSS** over JavaScript
- prefer **small, reviewable diffs** over broad cleanup

The goal is a site that is easy to read, easy to maintain, easy to extend, and reliable to publish through GitHub Pages.