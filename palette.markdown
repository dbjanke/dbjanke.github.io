---
layout: default
title: Palette
permalink: /palette/
palette:
  - name: Line Dried
    color: "#f9f4de"
    luma: "#f4f4f4"
  - name: Croissant
    color: "#fdcb85"
    luma: "#d2d2d2"
  - name: Tangy
    color: "#ffce01"
    luma: "#cccccc"
  - name: Orange Glow
    color: "#ffa501"
    luma: "#afafaf"
  - name: Sea Frolic
    color: "#53b5df"
    luma: "#a2a2a2"
  - name: Smoky Pitch
    color: "#536470"
    luma: "#616161"
  - name: Perfect Storm
    color: "#395c65"
    luma: "#555555"
  - name: Cadet Song
    color: "#334c57"
    luma: "#474747"
  - name: Blue Coal
    color: "#2b3140"
    luma: "#313131"
---

<style>
  .palette-page {
    display: grid;
    gap: 1rem;
  }

  .palette-note {
    margin: 0;
    color: #57606a;
    font-size: 0.95rem;
  }

  .palette-list {
    display: grid;
    gap: 0.35rem;
  }

  .palette-row {
    display: grid;
    grid-template-columns: minmax(9rem, 13rem) repeat(2, minmax(4.5rem, 6rem));
    align-items: center;
    gap: 0.35rem;
  }

  .palette-header {
    display: grid;
    grid-template-columns: minmax(9rem, 13rem) repeat(2, minmax(4.5rem, 6rem));
    gap: 0.35rem;
    align-items: end;
    font-size: 0.78rem;
    letter-spacing: 0.04em;
    text-transform: uppercase;
    color: #57606a;
  }

  .palette-name {
    margin: 0;
    font-size: 1rem;
    line-height: 1.2;
  }

  .palette-chip {
    height: 2.75rem;
    width: 100%;
    border-radius: 0.35rem;
    border: 1px solid rgba(0, 0, 0, 0.12);
    background: var(--chip-color);
  }

  @media (max-width: 36rem) {
    .palette-header,
    .palette-row {
      grid-template-columns: minmax(0, 1fr) repeat(2, minmax(4rem, 5rem));
    }
  }
</style>

<section class="palette-page">
  <p class="palette-note">Hover a swatch to inspect its hex value.</p>

  <div class="palette-list">
    <div class="palette-header" aria-hidden="true">
      <div>Name</div>
      <div>Color</div>
      <div>Luma</div>
    </div>
    {% for color in page.palette %}
      <article class="palette-row" aria-label="{{ color.name }}">
        <h2 class="palette-name">{{ color.name }}</h2>
        <div class="palette-chip" style="--chip-color: {{ color.color }};" title="{{ color.name }} color: {{ color.color }}"></div>
        <div class="palette-chip" style="--chip-color: {{ color.luma }};" title="{{ color.name }} luma: {{ color.luma }}"></div>
      </article>
    {% endfor %}
  </div>
</section>