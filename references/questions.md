# Questions, mathematical solutions, code, and diagrams

## Output according to question type

**Multiple choice:** transcribe the stem and every supplied option with its original letter. Identify all correct letters for a multiple-selection question. Add concise verification; do not hide options to save space. If no option is correct, say so and give the derived answer.

**Short answer:** show the result immediately when direct answers are requested. In a worked-solution collection, follow it with the formula and necessary steps. Provide plain input syntax separately if the answer field requires it.

**Fill-in blocks/dropdowns:** reproduce the equation's structure with actual visible boxes or a clear textual equivalent, e.g. `Σ([A] − [B] + 1)`. Label positions left-to-right, then top-to-bottom, unless the source already labels them. Give a position-to-value table and the completed equation. Flag a defective template rather than inserting mathematically false values.

## Mathematical solution sequence

1. Identify the given values, requested quantity, variables, domain, and assumptions.
2. State the formula or theorem before applying it.
3. Substitute with explicit bounds and parentheses.
4. Show each nontrivial transformation; retain terms until they are combined or bounded.
5. State the exact result and applicability conditions. Give an approximation or asymptotic class only when relevant.
6. Check with a second method or representative values where useful.

For example, a constant has not “disappeared” in a bound:

\[
100n+5\le100n+5n=105n\le105n^2\qquad(n\ge1).
\]

For a comparison, state the domain separately from the solution:

\[
100n<0.01n^2,\quad n>0
\iff100<0.01n
\iff n>10000.
\]

The condition n > 0 permits division; it does not make the initial inequality true for every positive n.

## Domain checks

- Probability: state support and assumptions, check normalization, derive integration limits from the support, and ensure conditional denominators are positive. Zero covariance does not generally prove independence.
- Graphs/automata: verify every transition, start/final node, alphabet, and reachable set. For NFA-to-DFA conversion, keep each DFA node's represented subset explicit when requested. Epsilon closure and symbol transitions are distinct operations; follow the source's table convention without omitting needed closure semantics.
- Data structures: check empty, singleton, first/last, full-capacity, and pointer-update cases. A drawing must agree with the code.
- Database schedules: identify exact operation positions, read-from relationships, initial reads, final writers, and conflict edges. Conflict serializability implies view serializability; the reverse does not generally hold. Only give an equivalent serial schedule when one exists under the claimed criterion.
- UML: use the current requirement IDs, consistent actors and names, and correct relationship semantics. Keep scenario and activity flows aligned. Do not add inheritance or unnecessary decision nodes merely for visual symmetry.

Read only checks relevant to the actual subject; these examples are not a requirement to cover all domains.

## Code and pseudocode

Match the requested language exactly: C++ is not C. Preserve provided ADT types, interfaces, file names, indexing conventions, and main-program format when requested. Separate `main.cpp`, implementation, and header clearly for copying. Keep pseudocode and implementation in distinct sections; if the user wants all pseudocode first, do that.

Use the requested loop style. Prefer while/for when that is the user's convention, but do not rewrite source semantics merely to avoid another construct. Explain a necessary convention briefly, such as whether stack top is an index or element count.

Compile and run meaningful small cases if execution tools exist. Otherwise inspect declarations, definitions, state updates, and boundary behavior, and say execution was not performed if claiming validation would matter. Avoid decorative comments and irrelevant features.

## Diagrams and tables

Use a deterministic graph/vector/diagram tool for exact technical relationships. Preserve source labels and requested geometry. A B+ tree should show node contents, levels, and leaf links; a finite automaton needs readable edge labels, an initial arrow, and final-state notation. Do not use a generative illustration as evidence of technical correctness.

Verify structure before styling. For exact table reproduction, preserve row/column order and the method shown in the slides, while explicitly correcting proven errors. Check that diagrams remain legible after export.
