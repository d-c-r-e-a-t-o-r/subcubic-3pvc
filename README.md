# A Polynomial-Space \(O(1.4289^n)\) Algorithm for 3-Path Vertex Cover on Subcubic Graphs

**Preprint. Not peer-reviewed. Comments and corrections are welcome.**

## Abstract

We observe that a greedy induced matching yields a dissociation set of size at least
\(n/3\) in every subcubic graph. Hence the minimum 3-path vertex cover has size at most
\(2n/3\). Combining this bound with the polynomial-space parameterized algorithm of
Červený and Suchý (arXiv:2111.05896), which runs in \(O^*(1.708^k)\) time, gives an
\(O^*(1.708^{2n/3}) = O(1.4289^n)\)-time polynomial-space algorithm for 3-path vertex
cover on subcubic graphs. This improves the previous polynomial-space bound
\(O(1.4613^n)\) of Chang et al. (2018). It does not improve the exponential-space bound
\(O(1.3659^n)\).

## Result

**Theorem.** Every subcubic graph on \(n\) vertices has a 3-path vertex cover of size at
most \(2n/3\), computable in polynomial time.

**Proof sketch.** Repeatedly pick an edge, add its endpoints to a set \(S\), and delete
the endpoints and all their neighbours (at most \(2+4=6\) vertices per step). The
endpoints of the chosen edges, together with the isolated vertices left at the end,
induce a matching plus isolated vertices, hence form a dissociation set. If \(t\) edges
are chosen, at most \(4t\) non-endpoint vertices are deleted and \(2t \le |S|\), so
\(n \le |S| + 4t \le 3|S|\), i.e. \(|S| \ge n/3\). The complement of \(S\) is a 3-path
vertex cover of size at most \(2n/3\). \(\square\)

**Algorithm.** Compute \(S\) as above and let \(k_0 = n-|S| \le 2n/3\). For
\(k=0,\dots,k_0\), run the \(O^*(1.708^k)\)-time polynomial-space decision algorithm of
Červený and Suchý, and return the first \(k\) that is feasible. The total time is
\(O^*(1.708^{2n/3}) = O(1.4289^n)\), polynomial space.

## Comparison

| Algorithm | Time | Space |
|---|---|---|
| Kardoš et al. 2011 | \(O^*(1.5171^n)\) | polynomial |
| Chang et al. | \(O^*(1.4658^n)\) | polynomial |
| Chang et al. 2018 | \(O^*(1.4613^n)\) | polynomial |
| Xiao–Kou 2017 | \(O^*(1.3659^n)\) | exponential |
| **This note** | \(\boldsymbol{O(1.4289^n)}\) | **polynomial** |

## Files

- `note_1.4289.pdf` — compiled 3-page note.
- `note_1.4289.tex` — LaTeX source.

## Compile

```bash
pdflatex note_1.4289.tex
```

## Status and caveats

- The result is specific to graphs of maximum degree 3.
- It improves the polynomial-space bound \(1.4613^n\) to \(1.4289^n\) (about \(2.2\%\)),
  but the exponential-space bound \(1.3659^n\) remains better.
- The argument is a black-box combination of a constructive dissociation-set bound and
  the current best FPT algorithm. It is elementary and may be folklore; a thorough
  novelty check has not been completed. Do not treat this as an established new record
  until the literature has been checked.
- To beat \(1.3659^n\), one would need a constructive dissociation set of size at least
  \(0.4175n\) (equivalently \(k/n \le 0.5825\)). The greedy construction gives \(n/3\).

## References

1. R. Červený, O. Suchý. Generating faster algorithms for \(d\)-Path Vertex Cover.
   arXiv:2111.05896, 2021.
2. D. Tsur. Parameterized algorithm for 3-path vertex cover. arXiv:1809.02636, 2018.
3. M.-S. Chang, L.-H. Chen, L.-J. Hung, Y.-Z. Liu, P. Rossmanith, S. Sikdar.
   Moderately exponential time algorithms for the maximum bounded-degree-1 set problem.
   Discrete Applied Mathematics, 2018.
4. M. Xiao, S. Kou. Exact algorithms for the maximum dissociation set and minimum
   3-path vertex cover problems. Theoretical Computer Science 657 (2017), 86–97.
5. M. Xiao, S. Kou. Kernelization and Parameterized Algorithms for 3-Path Vertex Cover.
   arXiv:1608.07022, 2016.
6. F. Kardoš, J. Katrenič, I. Schiermeyer. On computing the minimum 3-path vertex cover
   and dissociation number of graphs. Theoretical Computer Science 412 (2011),
   7009–7017.

## License

Text and figures: CC BY 4.0. LaTeX source: same.
