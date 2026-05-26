# 📜 Project_RED Visual Architecture & Contribution Guide

> **HEARKEN YE, DEVELOPERS:** This repository uses a strict decoupled architecture. The JavaScript engines and core functional mechanics are bound to explicit structural CSS selectors. Breaking the layout breaks the application. Follow these edicts carefully to maintain our Retro-Medieval-Modern visual balance.

---

## 🛑 Rule I: The Golden Separation (Structural Immunity)

You are here to paint the castle, not move the load-bearing stone walls. **Do not alter structural properties** on core component blocks.

- **Do NOT modify:** `position`, `top`, `left`, `z-index`, `display`, `transition`, `width`, `max-width`, or `overflow` configurations on global elements like `.side-panel`, `.side-panel-overlay`, `.node-container`, or `.panel-folder-content`.
- **The State-Class Edict:** The classes `.open` and `.active` are managed directly by DOM scripts. Modifying their core css configuration breaks layout execution.

---

## 🎨 Rule II: The Retro-Medieval-Modern Design Spectrum

All visual contributions must strictly align with our hybrid design ecosystem:

1.  **Chunky 90s Geometry:** **Never** add modern border-radii (`border-radius`). Elements must remain sharp, rectangular, and tactile (radius = 0px).
2.  **Double-Borders & Dashes:** Use `border: 3px double var(--border-color);` for major header separations, and `dashed` lines for sub-containers or technical divisions to honor the scriptorium parchment feel.
3.  **High-Density Scannability:** Content spacing must remain compressed and dense. Avoid large, airy gaps. Use `text-align: justify;` for long-form paragraphs to emulate tightly packed printed ledger columns.

---

## 🧱 Rule III: The Token Declaration Standard

When mapping or expanding UI components, you **must** use the design engine's design tokens. Hardcoded hex values inside elements will fail production review.

### Color Matrix Mapping Reference

| Design Token          | Dark Mode Intent (Dungeon Master)       | Light Mode Intent (Royal Codex)     |
| :-------------------- | :-------------------------------------- | :---------------------------------- |
| `var(--bg-base)`      | Deep Dungeon Void (`#0B0C10`)           | Royal Parchment Cream (`#F4EFE6`)   |
| `var(--bg-surface)`   | Cast Iron Structural Plates (`#12141C`) | Fresh Vellum Paper (`#FCFAF2`)      |
| `var(--border-color)` | Burnished Guild Gold (`#E2B13C`)        | Blacksmith Charcoal Ink (`#2B261F`) |
| `var(--accent-color)` | Flagship Interactive Accent (`#E2B13C`) | Wax Seal Crimson (`#9E2A2B`)        |

```css
/* ❌ VIOLATION: Hardcoded aesthetic layout properties */
.custom-widget {
  background-color: #1a1a1a;
  border-radius: 8px;
  box-shadow: 0px 4px 20px rgba(0, 0, 0, 0.5);
}

/*  CORRECT: Adhering to the token map and sharp geometry */
.custom-widget {
  background-color: var(--bg-surface);
  border: 1px solid var(--border-color);
  border-radius: 0px;
}
```

---

## ✍️ Rule IV: Typographic Hierarchies

Our technical presentation uses a split typographic strategy to enforce information prioritization:

- **Structural Data & Labels:** All headers (`h1`, `h2`, `h3`), meta labels, folder paths, and action triggers **must** be pinned to monospace configurations (`ui-monospace, SFMono-Regular, monospace`) and set to heavy, blocky `uppercase`.
- **Reading Content:** Paragraphs and documentation lists within `.markdown-body` use system sans-serif font-stacks to preserve processing speed and avoid reading exhaustion.

---

## ⚔️ Pull Request Submission Protocol

Before filing a pull request for a UI expansion or custom skin, complete this verification checklist:

- [ ] **The Toggle Test:** Does the element gracefully transform without text bleed when switching between `data-theme="dark"` and `data-theme="light"`?
- [ ] **The Script Verification:** Open your browser console. Are any interactive elements or hooks failing due to modified or missing selectors?
- [ ] **The Constraint Check:** Confirm no layout-breaking properties (`position`, `z-index`, `display`) were injected into your layout configuration files.
