# Inapproximability of Treedepth, Treewidth, and Total Elimination Depth

The manuscript is assembled by `main.tex` from the files in `sections/`.
Its bibliography is `references.bib`.

## Main results

The paper proves deterministic approximation hardness on simple,
unweighted graphs of bounded maximum degree:

| Parameter | NP-hardness | Ordinary UGC | SSEH |
| --- | --- | --- | --- |
| Treedepth | below `18/17` | below `4/3` | every fixed factor |
| Treewidth | below `12/11` | below `4/3` | every fixed factor |
| Total elimination depth | below `63/62` | below `8/7` | every fixed factor |

The degree bound may depend on the excluded approximation factor.

Minimum total hierarchical customizable-label size and minimum total CCH
upward vertex search-space size equal total elimination depth. Their total
and average objectives therefore inherit its NP, UGC, and SSE hardness
ranges, including on bounded-degree and regular graphs. Search spaces count
the starting vertex. The applications section supplies polynomial decoding
from hierarchical labels to elimination forests.

General factor sparsification assumes bounded factor incidence and bounded
degree of retained edges; it requires no balance assumption on biclique
sides. The connected replacement lemma retains its separate balance
hypothesis. Search applications distinguish mandatory target confirmation
from free singleton identification; their summed optima differ by at most
the graph order, which the quadratic hardness gaps absorb.

After implementing the October 22 audit improvements, further research in
this workspace is focused only on hardness results and stronger hardness
bounds.

Prioritize simple proofs and qualitative gains. Omit ancillary refinements
that only improve constants or finite-size estimates without changing the
main hardness thresholds, hypotheses, or scope. Use sufficient coarse
bounds while keeping correctness and nontrivial calculations explicit.
For long mechanical gap calculations, give the shortest useful proof
sketch in the main text and place the full derivation in the appendix,
with a precise cross-reference. Display successive transformations as
one arrow chain on one line when it fits; put lengthy citations in the
surrounding prose.

All three NP-hardness reductions use the bounded-occurrence parity source
stated in [sections/np-hardness.tex](sections/np-hardness.tex).
Treedepth and treewidth share a parity-witness graph; total elimination
depth uses a separate encoding by literal blocks and auxiliary pairs in
[sections/np-total-depth-hardness.tex](sections/np-total-depth-hardness.tex).

## Manuscript structure

- The main text presents the UGC results, then SSE hardness, NP-hardness,
  bounded-degree reductions, applications, and open questions.
- `sections/appendix-source-normalizations.tex` contains the source-promise
  normalizations and the provenance discussion for the NP reductions.
  The parity normalization pairs the source with a complemented copy and
  repeats each equation six times, preserving its satisfied fraction.
- `sections/appendix-auxiliary-proofs.tex` contains the branching
  inequalities, the anchor-length derivation, and the total-depth
  normalization and path identities, followed by the factor-replacement
  construction.
- `sections/appendix-dense-gap-calculations.tex` gives the full parameter
  choices and arithmetic for the dense hardness gaps.
- `sections/appendix-transfer-gap-calculations.tex` gives the gap
  calculations for sparsification, regularization, and subdivision;
  `sections/appendix-application-gap-calculations.tex` continues that
  appendix with the binary state-space application.

In proof calculations, put the relevant theorem, lemma, or equation
reference above each nontrivial equality or inequality transition, using
`\overset`. State theorem, lemma, proposition, and corollary bounds without
these annotations; give their justifications in the proofs. Keep direct
arithmetic steps plain and retain explicit sum domains. Do not use
`\substack` or framed bounds.

Use a connected directed graph with shared nodes for the introduction's
reduction overview. Keep sources and constructions in aligned columns,
merge the parameter gaps before degree reduction, and show only the main
application branches. Keep specialized routes in the surrounding text.

Define mathematical assignments, probabilities, and guarantees by explicit
formulas, with their domains and parameters. When following a published
construction, credit its idea before stating the actual construction used
here. Specify the base measures and independence assumptions of samplers.

Build from this directory with:

```powershell
latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex
```

The command writes `main.pdf` in this directory.
