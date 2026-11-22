# Study-Note Structure and Readability

## Coverage and Organization

- **Complete module coverage by default:** When summarizing a university module, chapter, or slide deck into a PDF, Word doc, or full Markdown notes, include **all** substantive topics, definitions, rules, formulas, tables, diagrams, and key examples from the source unless the user explicitly asks to filter or shorten scope. Do not drop conceptual or non-calculation material just because formulas are easier to extract.
- **Follow requested grouping and concept dependency:** Respect requested week, chapter, module, or task numbering. Within each section, order ideas so prerequisites come before dependent concepts. When one topic is the user's focus, keep earlier prerequisite material compact and link back to it instead of repeating an entire earlier chapter.
- **First-pass exercise alignment:** If quizzes, assignments, or past exam questions are supplied alongside slides, inventory what they test first so the summary explicitly covers and highlights those concepts.

## Topic Anatomy (Full Notes: PDF / Word / Markdown)

For each substantial topic, use this natural learning sequence (adapting to the user's request):

1. **Concrete anchor + concise meaning:** Explain *"what is X?"* through a tiny, concrete example before or alongside a short definition.
2. **Rules, symbols, and conditions:** List formulas, symbol definitions, assumptions, and when the rule applies (or fails).
3. **Worked example from the source:** Reproduce the problem/code accurately with an unobtrusive source citation (e.g., *Slide 14* or *Module 3, p. 8*), then solve step by step. Place examples directly under their topic unless the user requests a separate exercise section at the end.
4. **Distinctions, memory cues, and traps:** Highlight confusable pairs, recognition cues, and common exam mistakes.
5. **Additional examples (optional):** Add new examples only when requested or needed to illustrate an uncovered edge case; always label them clearly as **New / Additional Example**.

Keep explanatory prose short and connected; do not turn every single sentence into a bullet, and do not skip nontrivial mathematical transformations. Explain steps that change a counting model, domain, probability assumption, summation bound, or algorithm behavior rather than narrating trivial arithmetic.

## High-Value Study Patterns

Use these selectively where they genuinely clarify the material (never as filler):

- **Confusable-Term Comparison Tables:** Put easily confused concepts side-by-side (`Criterion | Concept A | Concept B`), e.g., `O` vs. `Ω` vs. `Θ`, Stack (LIFO) vs. Queue (FIFO), NFA vs. DFA, Conflict vs. View Serializability, Inclusive vs. Exclusive Bounds.
- **Memory Cues & Exam Traps:** Compact bullets describing *when* a method applies and the exact mistake to avoid—not vague slogans.
- **Visual Diagrams & Charts:** Use clean flowcharts, trees, state diagrams, or simple graphs whenever relationships, hierarchies, or growth trends are clearer visually than in prose.
- **Quick Self-Check (optional):** Only when appropriate for a study guide or requested by the user, include 1–2 brief active-recall prompts per major section—never bloat a concise summary with unrequested quizzes.

## Adapting Structure by Format

- **PDF / Word Full Summary:** Full conceptual spine + all module topics + worked examples + comparison tables + clean diagrams. Concise prose, zero fluff.
- **PPT / PPTX Presentation Summary:** Compress each topic into **point-by-point slides** (short headline takeaways, visual cues, diagrams/graphs, comparison tables, formula spotlights). Split dense topics across multiple clean slides instead of shrinking text or pasting paragraphs. Keep detailed derivations or commentary in speaker notes.
- **Summary Images (PNG/JPG):** Focus each image on a cohesive unit (one module overview, one comparison matrix, one formula sheet, or one concept diagram) so typography stays crisp and uncluttered.
- **Cheatsheet:** Create a separate artifact when requested. Use a compact lookup structure:

| Situation / Trigger | Formula / Rule | Condition / Assumption | Tiny Example |
|---|---|---|---|
| Recognizable cue | Readable notation | Domain or boundary | One substitution → result |

Keep derivations in the full notes. Use compact layout rather than shrinking fonts until unreadable. For power sums or named rules, always show the explicit expression alongside any course label (never just `"S2"`).

## Revision Behavior

Treat user feedback as a targeted update. Preserve approved sections, examples, numbering, language, and format unless the user asks to change them or a factual correction requires it. Recheck affected cross-references and totals. Never respond to *"add this below"* by deleting or rewriting earlier approved text.
