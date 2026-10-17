# Approximation Hardness of Treedepth

The article is assembled by `main.tex` from `sections/`.
Its bibliography is `references.bib`.

For each fixed factor in the following ranges, the paper proves hardness
on simple unweighted graphs of maximum degree bounded by a constant
depending only on that factor:

| Parameter | NP-hardness | Ordinary UGC | SSEH |
| --- | --- | --- | --- |
| Treedepth | below 18/17 | below 4/3 | every fixed constant |
| Treewidth | below 12/11 | below 4/3 | every fixed constant |

The reductions are deterministic. The degree bound is not uniform over
all excluded factors. The SSE results are related explicitly to the
earlier construction and constant-degree source of Wu, Austrin,
Pitassi, and Liu. No improvement above the NP factor 18/17 is claimed.

The main text presents the layered UGC reduction, the line-graph SSE
proof, and applications. Equivalent formulations of treedepth are
background, without separate result statements. Direct parameter
transfers are brief consequences.

- Appendix A, `sections/03-np-hardness.tex`, gives the dense NP
  construction. Its provenance subsection identifies inherited ideas
  from Bonnet, Neuen, and Sokolowski and the changes to the witnesses,
  block sizes, and anchors.
- Appendix B, `sections/appendix-treewidth.tex`, proves the dense
  treewidth bounds by a shared replication lemma. The multipartite
  source threshold is credited to Berczi et al.; an elementary product
  supplies an alternative derivation from Khot-Regev.
- Appendix C, `sections/appendix-source-normalizations.tex`, derives
  the normalized source promises. Its final subsection, in
  `sections/appendix-bounded-degree-ugc-source.tex`, gives a deterministic
  bounded-degree independent-set source from the AKS density theorem,
  BSS spectral sparsification, and downward rounding.
- Appendix D, `sections/appendix-auxiliary-proofs.tex`, contains the
  numerical branching inequality and the incidence-construction
  derivation. Its final subsection, in `sections/appendix-bss-rational.tex`,
  supplies a rational implementation with polynomial bit complexity.
- Appendix E, `sections/appendix-expander-sparsification.tex`, proves
  clique and biclique completion lemmas for elimination forests and
  deterministic expander replacements at arbitrary factor sizes.
  It derives all three bounded-degree treedepth results. The NP result
  answers Conjecture 1 of Schirrmacher, Siebertz, and Vigny (MFCS 2025).
- Appendix F, `sections/appendix-bounded-degree-treewidth.tex`, proves
  the corresponding tree-decomposition lemmas and bounded-degree
  treewidth results. The NP proof uses five local completion factors
  per variable, giving total loss 39 xi Rm.

Applications are in `sections/05-applications.tex`, including the
added-edge trivially perfect completion argument. Dense constructions
are retained where applications use their specific representations;
bounded degree is not asserted for every application.

Incomplete investigations, alternative constructions, and obstructions
remain outside the article in `../partial-results-and-notes/`.

Build from this directory:

```powershell
latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex
```

The delivered PDF is `../output/pdf/conditional-approximation-hardness-treedepth.pdf`.
