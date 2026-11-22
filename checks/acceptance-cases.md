# Behavioral Acceptance Cases

These are evaluation cases, not a claim of cross-platform execution. Run them with an assistant using the skill and inspect the observable result. Do not grade by requiring exact prose or heading strings.

## 1. Count Only the Requested Operation

Input: count prints in `for i = 2 to 10n: print("Hello")`, inclusive integer bounds and `n >= 1`. Then ask whether loop-condition checks add to that answer.

Expected: exact print count `10n - 1`; conditions do not add prints. A fuller instruction model is treated separately, with explicit costs.

## 2. Duplicate Versus Variant

Input: two identical images of that loop and one image with start `i = 3`.

Expected: two unique questions, a mapping of the identical images, and a distinct answer `10n - 2` for the variant. No missing original number is invented.

## 3. Broken Summation Template

Input: `Σ(i=0..n-3) Σ(j=i+3..n-3) 2`, with `n >= 6`. The provided template replaces every inner count with `n - i - 5` across the full outer range.

Expected: identify empty inner ranges and do not count them negatively. Only `i = 0..n-6` contribute, giving `2 Σ(i=0..n-6)(n-i-5) = (n-5)(n-4)`. Mark the template's invalid step rather than force its blanks to fit.

## 4. Choice Fidelity

Input: “What characterizes O(1)? a. Cost does not grow with input size. b. Exactly one operation always. c. Input must have one element.”

Expected: preserve all options, choose `a`, and explain briefly why a constant cost need not equal one operation.

## 5. Quotation Fidelity

Input: a paragraph without author/year; request a direct quote with author/year and an Indonesian explanation.

Expected: quote only supplied wording, distinguish the explanation from the quotation, and identify missing attribution. No invented author/year or translated quote disguised as the original.

## 6. Language and Artifact Contract

Input: request an English summary, Indonesian cheatsheet, and two separate PDFs. Later request adding one example without changing existing approved text.

Expected: maintain both language/format contracts, make a targeted addition, check cross-references, and report only actual file/render verification. If PDF export is unavailable, state that limitation instead of pretending a Markdown response is a PDF.

## 7. Average-Case Assumptions

Input: successful sequential search, `n` equally likely target positions; then introduce failure probability `p`.

Expected: first average `(n+1)/2`. With remaining successful positions uniform, average `(1-p)(n+1)/2 + pn`. No unjustified extra division by `n`.

## 8. Incorrect Asymptotic Claim

Input: decide whether `100n+5` belongs to `Omega(n²)`, showing `c g(n)` on the right.

Expected: disprove the claim for positive `c` using `(100n+5)/n²` tending to zero, or an equivalent argument. One failed choice of `c` is not enough. Do not equate Omega with best case.

## 9. Presentation Summary (PPTX) — Point-by-Point & Clean Visuals

Input: a 15-page university module on sorting algorithms (comparison, complexities, divide-and-conquer flow); request a PPTX summary deck in Indonesian.

Expected: scannable point-by-point slides (not full-text paragraphs), varied layouts (comparison table, process diagram or growth chart, concise bullets), clean flat high-contrast color palette with **no weird color gradients**, legible font sizes, and rendered slide inspection performed before delivery.

## 10. Full Module PDF — Concise and Complete Coverage

Input: a multi-section lecture module containing definitions, 3 theorems, 1 conceptual comparison table, and 2 worked examples; request a concise PDF study summary without narrowing scope.

Expected: all sections, definitions, theorems, comparison table, and worked examples from the module are included accurately without dropping non-math concepts; prose is concise and clear; math is properly typeset (no raw LaTeX); visual QA confirms no clipping or broken layout.

## 11. Visual Study Card / Summary Image

Input: request a PNG summary card comparing Stack (LIFO) vs. Queue (FIFO) with operations and complexities.

Expected: high-resolution, uncluttered visual card using a flat high-contrast palette (no weird gradients), deterministic layout/diagram, crisp legible labels without overlap, and accurate operation complexities.

## 12. Programming Summary — Notasi Algoritmik (Rinaldi Munir ITB / Telkom University) + Go / C++

Input: a Data Structures module on Singly Linked List (`insertFirst`, `deleteLast`) with a Telkom University pseudocode sample using `=` assignment, `==` equality, `P->next`, and `{ I.S. / F.S. }`; request both pseudocode and a Go or C++ implementation.

Expected: pseudocode strictly follows the supplied Rinaldi Munir / Telkom University style (`type`, `procedure`, `input/output`, `Kamus`, `Algoritma`, `endprocedure`, `NIL`, `P->next`) with zero Go/C++ syntax leakage; the Go or C++ implementation sits in a separate, clean, compilable section with matching logic and edge-case handling (empty list, single node).
