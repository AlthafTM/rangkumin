# Algorithm-analysis conventions and checks

## Declare what T(n) counts

T(n) can mean executions of a specified important operation or the cost of a fuller instruction model. It is not automatically every machine operation. Follow the question's definition.

- If `println` is the important operation, count only executed prints. Loop conditions and increments do not add prints.
- If `op` denotes an arithmetic operation, count the requested arithmetic operations. In `sum = sum + (i+2)/i`, there are three arithmetic operations per body execution; assignment and loop control are separate unless included by the cost model.
- For a fuller model, list instruction costs and execution frequencies. A swap may be one abstract operation or three assignments. State which model is used.
- A condition is counted when evaluated; its branch body is counted only when executed. Respect short-circuit evaluation and early exits.
- A loop without a print can still alter later print counts through state changes. Inspect behavior rather than deleting every non-print line from consideration.

## Count before simplifying

For unit steps, integer bounds, and a nonempty interval:

\[
\sum_{i=a}^{b}1=b-a+1,
\qquad
\sum_{i=a}^{b-1}1=b-a.
\]

For potentially empty loops, the execution count is max(0, b-a+1) or max(0, b-a), respectively. Do not report a negative number of operations. State the n-range when giving a polynomial that assumes all relevant loops run.

For sequential blocks, add their counts. For nested loops, use sums with their actual dependencies:

\[
T(n)=\sum_{i=a}^{b}\left(p+\sum_{j=c(i)}^{d(i)}q(i,j)\right).
\]

Do not multiply independent bounds when an inner bound depends on the outer index. Identify a print after the inner loop separately from prints inside it. With ordinary termination, a loop body that runs m times generally has m+1 condition evaluations; this applies only when condition evaluations belong to the selected model. Breaks and short-circuit conditions require their actual evaluation paths.

## Summation rules

Show the applicable sigma expression, not just a formula nickname. Preserve R1/S1/etc. only if supplied by the source.

\[
\sum_{i=1}^{n}c=cn,\quad
\sum_{i=1}^{n}i=\frac{n(n+1)}2,\quad
\sum_{i=1}^{n}i^2=\frac{n(n+1)(2n+1)}6,
\quad\sum_{i=1}^{n}i^3=\left(\frac{n(n+1)}2\right)^2.
\]

For shifted bounds, subtract prefix sums. For linearity, distribute constants and addition over the same bounds. Include higher-power sums, geometric series, logarithm rules, or calculus methods only when relevant to the supplied material. Verify any higher-power formula independently before using it.

## Logarithmic loops

Distinguish addition from multiplication. For `i = 1; while i <= n: i *= b`, integer n >= 1 and b > 1, the body count is floor(log_b n)+1. Adding b each time is generally linear, not logarithmic. For strict inequalities, a different start, division, integer rounding, or early exits, derive the stopping inequality before choosing floor/ceiling.

## Best, worst, average

Hold input size n fixed while comparing inputs. Best and worst are the minimum and maximum costs over those inputs. Average is an expectation under a stated distribution:

\[
T_{avg}(n)=\sum_xP(x)T(x).
\]

Only for m equally likely cases does this become `(1/m) Σ T(x)`. For successful sequential search with each of n positions equally likely:

\[
T_{best}(n)=1,\quad T_{worst}(n)=n,\quad
T_{avg}(n)=\frac1n\sum_{i=1}^{n}i=\frac{n+1}2.
\]

If failure is possible, include its probability and cost. A fixed comparison count, as in standard selection sort, can be the same in all cases; do not multiply a deterministic count by 1/n simply because “average” appears.

## Asymptotic notation

Use consistent inequalities; keeping the comparison expression on the right is a useful presentation convention:

\[
T\in O(g)\iff\exists c>0,n_0:\ 0\le T(n)\le c g(n)\quad(n\ge n_0),
\]
\[
T\in\Omega(g)\iff\exists c>0,n_0:\ T(n)\ge c g(n)\ge0\quad(n\ge n_0),
\]
\[
T\in\Theta(g)\iff\exists c_1,c_2>0,n_0:
\ T(n)\ge c_1g(n)\ge0\ \text{and}\ T(n)\le c_2g(n)\quad(n\ge n_0).
\]

The comparison is with c g(n), not bare g(n). Big-O is an upper bound, Omega a lower bound, and Theta a tight bound. They are not synonyms for worst, best, and average cases. Give the tight class when growth rate is requested and proved; use the notation the question specifically asks for. A loose upper bound may be true without being tight.

To disprove membership, show why no positive constant and threshold can satisfy the inequality, for example via an unbounded ratio. Do not treat one failed choice of c as a proof that Big-O is false.

For sufficiently large n, common increasing growth classes are:

\[
1\prec\log n\prec n\prec n\log n\prec n^2\prec n^3\prec 2^n\prec n!.
\]

Finite-input speed can differ because of constants; solve the actual inequality for a crossover. Distinguish exact counts, assumptions, and asymptotic claims in the final answer.

## Verification

Enumerate the selected operation directly for small valid n, including values near each loop's starting threshold. Compare with the derived expression, not a copy of its derivation. Check nested reset locations and indentation against the source. When a printed summation includes empty inner intervals, count those as zero; a term-count formula valid only for nonempty ranges cannot be applied blindly across the whole outer range.
