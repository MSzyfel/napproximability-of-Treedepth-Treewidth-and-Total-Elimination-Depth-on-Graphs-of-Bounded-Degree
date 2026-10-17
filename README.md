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
| Total elimination depth | some `1 + ε₀ > 1` | below `8/7` | every fixed factor |

The reductions are deterministic. The degree bound may depend on the
excluded approximation factor.

## Manuscript structure

- The main text presents the UGC results, then SSE hardness, NP-hardness,
  bounded-degree reductions, applications, and open questions.
- `sections/appendix-source-normalizations.tex` contains the source-promise
  normalizations and the provenance discussion for the NP reduction.
- `sections/appendix-auxiliary-proofs.tex` contains the earlier incidence
  construction argument, the branching inequalities, and the anchor-length
  derivation.

Build from this directory with:

```powershell
latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex
```

The command writes `main.pdf` in this directory.
