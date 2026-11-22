# Artifact Creation and Visual Quality

## Format Selection and Contracts

Choose the exact artifact format requested by the user. Never substitute PDF for editable Word, Markdown text for a requested file, or a file when the user asked for chat text only. Keep full study notes and compact cheatsheets in separate files when requested.

- **PDF:** Fixed, print- and screen-ready study guide or cheatsheet. Concise, clear, and complete across all module material unless narrowed.
- **PPT / PPTX:** Presentation or quick-review slide deck. Point-by-point scannability with visual cues, clean diagrams, and charts/graphs.
- **Word / DOCX:** Editable study document, report, or template-based submission.
- **Images (PNG / JPG / SVG):** Visual study cards, infographics, concept maps, formula sheets, comparison tables, or technical diagrams.

### Templates and Originals
- When given a template, inspect its page/slide size, margins, fonts, heading hierarchy, numbering, table style, cover, and logos before editing. Preserve approved structure.
- Use only verified or provided identity details; never invent a class code, student ID, author, or institutional label.
- Keep original files untouched unless replacement is explicitly requested. Use clear, descriptive output filenames in the requested destination. Never embed private identifiers or course files in public examples.

---

## Visual Design and Color Hygiene (Applies to All Visual Outputs)

Good study visuals reduce cognitive load. Every slide, diagram, chart, PDF callout, and summary image must follow these rules:

- **Flat, restrained, high-contrast palettes:** Use a clean neutral canvas (white or very soft off-white `#FAFAFA` / `#F8FAFC` for light mode; deep slate `#0F172A` only if dark mode is requested), dark readable body text (`#1E293B` or `#111827`), **1 primary accent color** (e.g., navy, slate blue, deep teal, or forest green), and at most **1–2 muted supporting tints** for callouts, tables, or chart series.
- **No weird color gradients:** Do **not** use rainbow gradients, neon glows, multi-stop purple/pink/cyan AI-style backgrounds, gradient text fills, or low-contrast gradient boxes behind text or charts. Prefer clean solid fills and crisp 1px subtle borders.
- **Purposeful visual cues:** Use icons, color-coded badges, arrows, callout boxes, and highlights only to signal real meaning (e.g., formula, key distinction, exam trap, step sequence)—never as filler decoration.
- **Generous whitespace:** Leave clear margins and breathing room between blocks. Crowded pages and slides hurt comprehension more than an extra page or slide.

---

## Format-Specific Standards

### 1. PDF (Study Guides & Cheatsheets)
- **Complete yet concise:** Cover all topics, definitions, formulas, tables, and key examples from the module unless the user narrows scope, while keeping prose tight and scannable.
- **Typography & math:** Render mathematical notation properly (large sigma bounds, fractions, powers, Greek letters, subscripts). Raw LaTeX source commands are never acceptable in a finished PDF. Use readable body size (10–11pt), strong contrast, comfortable line spacing (1.35–1.5), and clear visual hierarchy.
- **Code & tables:** Keep code monospaced, properly indented, and unbroken across pages where possible (prefer splitting at function boundaries over shrinking text). Fit table columns to content, repeat headers across page breaks, and avoid orphan headings or fragmented rows.
- **Page rhythm:** Avoid half-empty accidental breaks or excessive blank pages, but never shrink fonts into illegibility just to force a page count.

### 2. PPT / PPTX (Presentations & Review Decks)
- **Point-by-point, never full text:** Slides are visual anchors, not printed textbooks.
  - Keep bullets short and scannable (aim for **3–5 points per slide**, ~8–15 words per point, bold lead-in phrase + concise takeaway).
  - Never paste full study-guide paragraphs onto a slide. Put extended explanation, proofs, or verbal commentary in **speaker notes** when helpful.
- **Visual cues, diagrams, and graphs:**
  - Use clean flowcharts, architecture/process diagrams, comparison tables, timeline/step strips, or quantitative charts/graphs (bar, line, growth-rate curves, trees, state diagrams) whenever relationships, processes, or trends are being explained.
  - Every chart or diagram must have legible axis/node labels, clear units, and clean flat colors matching the deck palette.
- **Layout variety:** Do not repeat the same plain title + bullet wall on every slide. Choose layouts that fit the content:
  - 2-column comparison (e.g., `Concept A vs. Concept B`, `Before vs. After`)
  - Visual + Takeaways split (diagram/graph on one side, 3–4 crisp bullets on the other)
  - Process / step flow cards (3–4 numbered horizontal steps)
  - Formula / theorem spotlight (clean boxed equation + symbol key + tiny example)
  - Compact summary / recap grid
- **Readability:** Maintain generous margins, consistent alignment, and large readable fonts (titles ~24–32pt, body ~16–20pt, captions/labels >= 12–14pt; never tiny 9–10pt slide text).

### 3. Word / DOCX (Editable Notes & Reports)
- Use native semantic styles (`Heading 1/2/3`, real bulleted/numbered lists, editable tables, proper page breaks). Never simulate layout with repeated blank paragraphs or manual spaces.
- Keep formulas clean and readable (native OMML equations or crisp high-DPI inline/block math where supported).
- Preserve full editability so the user can annotate, reformat, or copy sections effortlessly.

### 4. Summary Images & Diagrams (PNG / JPG / SVG)
- **High clarity and resolution:** Export at high DPI (e.g., 2x–3x scale or 300 DPI for print/dense tables) so every formula, subscript, and node label is sharp without zooming excessively.
- **Clean composition:** Use a clear title header, structured grid or flow sections, crisp card borders or subtle flat tinted boxes, generous padding, and consistent typography.
- **Deterministic technical accuracy:** Use deterministic code/vector/diagram tools (SVG, Matplotlib, Graphviz, Mermaid, Pillow/HTML-to-PNG) for formulas, charts, trees, automata, schedules, and tables. Never rely on a generative image model to render text-heavy summaries or technical diagrams where exact symbols matter.
- **Clean color discipline:** Same flat high-contrast palette rule—no weird gradients, no dark muddy overlays behind text, no clashing saturated colors.

---

## Render, Inspect, Repair (Mandatory Visual QA)

1. **Generate** the requested artifact using the host's best available document, slide, diagram, or image tools.
2. **Verify integrity:** Confirm the output file exists, is non-empty, and opens/parses cleanly.
3. **Render every page/slide/image:** Convert PDF/DOCX/PPTX pages to images (contact sheet for overview plus close-up inspection for dense equations, code, tables, and diagrams).
4. **Inspect visually** for:
   - Missing glyphs, raw LaTeX tokens, or broken math alignment
   - Text clipping, box overflow, overlapping shapes/labels, or awkward line wraps
   - Wall-of-text slides (in PPTX) or cramped layouts
   - Weird/muddy gradients, low text contrast, or clashing colors
   - Broken table columns, split code blocks, page-number errors, or excessive blank space
5. **Repair and re-inspect** every modified page/slide until clean.
6. **Verify content fidelity separately:** Cross-check extracted text/content against the working coverage map so no required topic, formula, option letter, block label, or conclusion was lost during export. A clean layout does not verify mathematical correctness.

If rendering or a requested export format is unavailable in the current environment, state that exact limitation clearly and offer a usable alternative. Never claim visual QA passed merely because a file was written to disk.

---

## Delivery and Revision

- Return concise, clickable paths to the generated file(s) and only essential notes. Do not narrate routine tool calls.
- For revisions, update only the requested scope and affected cross-references without deleting unrelated approved sections.
- Report only checks actually performed. Publishing, emailing, uploading, or overwriting originals requires explicit authorization.
