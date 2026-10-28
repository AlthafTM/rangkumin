# Behavioral acceptance cases

These are evaluation cases, not a claim of cross-platform execution. Run them with an assistant using the skill and inspect the observable result. Do not grade by requiring exact prose or heading strings.

## 1. Count only the requested operation

Input: count prints in `for i = 2 to 10n: print("Hello")`, inclusive integer bounds and n >= 1. Then ask whether loop-condition checks add to that answer.

Expected: exact print count 10n - 1; conditions do not add prints. A fuller instruction model is treated separately, with explicit costs.

## 2. Duplicate versus variant

Input: two identical images of that loop and one image with start i = 3.

Expected: two unique questions, a mapping of the identical images, and a distinct answer 10n - 2 for the variant. No missing original number is invented.

## 3. Broken summation template

Input: `Σ(i=0..n-3) Σ(j=i+3..n-3) 2`, with n >= 6. The provided template replaces every inner count with n - i - 5 across the full outer range.

Expected: identify empty inner ranges and do not count them negatively. Only i = 0..n-6 contribute, giving 2 Σ(i=0..n-6)(n-i-5) = (n-5)(n-4). Mark the template's invalid step rather than force its blanks to fit.

## 4. Choice fidelity

Input: “What characterizes O(1)? a. Cost does not grow with input size. b. Exactly one operation always. c. Input must have one element.”

Expected: preserve all options, choose a, and explain briefly why a constant cost need not equal one operation.

## 5. Quotation fidelity

Input: a paragraph without author/year; request a direct quote with author/year and an Indonesian explanation.

Expected: quote only supplied wording, distinguish the explanation from the quotation, and identify missing attribution. No invented author/year or translated quote disguised as the original.

## 6. Language and artifact contract

Input: request an English summary, Indonesian cheatsheet, and two separate PDFs. Later request adding one example without changing existing approved text.

Expected: maintain both language/format contracts, make a targeted addition, check cross-references, and report only actual file/render verification. If PDF export is unavailable, state that limitation instead of pretending a Markdown response is a PDF.

## 7. Average-case assumptions

Input: successful sequential search, n equally likely target positions; then introduce failure probability p.

Expected: first average (n+1)/2. With remaining successful positions uniform, average (1-p)(n+1)/2 + pn. No unjustified extra division by n.

## 8. Incorrect asymptotic claim

Input: decide whether 100n+5 belongs to Omega(n²), showing c g(n) on the right.

Expected: disprove the claim for positive c using (100n+5)/n² tending to zero, or an equivalent argument. One failed choice of c is not enough. Do not equate Omega with best case.
