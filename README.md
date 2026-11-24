# A Polynomial-Space \(O(1.3069^n)\) Algorithm for 3-Path Vertex Cover on Subcubic Graphs

**Preprint. Not peer-reviewed. Comments and corrections are welcome.**

## Abstract

A known lower bound on the dissociation number gives
\(\operatorname{diss}(G) \ge n/\lceil(\Delta+1)/2\rceil\) for every graph of maximum
degree \(\Delta\); for subcubic graphs this is \(\operatorname{diss}(G) \ge n/2\).
Hence the minimum 3-path vertex cover has size at most \(n/2\). Combining this bound
with the polynomial-space parameterized algorithm of Červený and Suchý
(WG 2023; arXiv:2111.05896), which runs in \(O^*(1.708^k)\) time, gives an
\(O^*(1.708^{n/2}) = O(1.3069^n)\)-time polynomial-space algorithm for 3-path vertex
cover on subcubic graphs. This improves both the previous polynomial-space bound
\(O(1.4613^n)\) of Chang et al. (2018) and the exponential-space bound
\(O(1.3659^n)\) of Xiao and Kou (2017).

## Result

**Lemma (Brešar et al. 2011, Theorem 6 and Corollary 7).** If \(G\) has maximum
degree \(\Delta\), then \(\operatorname{diss}(G) \ge n/\lceil(\Delta+1)/2\rceil\).
In fact, \(V\) can be partitioned in \(O(|E(G)|)\) time into
\(\lceil(\Delta+1)/2\rceil\) sets each inducing a subgraph of maximum degree at most
\(1\); the largest such set is a dissociation set of size at least
\(n/\lceil(\Delta+1)/2\rceil\). See also Bock, Pardey, Penso, and Rautenbach
(J. Graph Theory, 2023).

**Corollary.** Every subcubic graph satisfies \(\operatorname{diss}(G) \ge n/2\), hence
the minimum 3-path vertex cover has size at most \(n/2\). The bound is tight: \(K_4\)
has dissociation number \(2 = n/2\).

**Algorithm.** Let \(k_0 = \lfloor n/2 \rfloor\). For \(k=0,\dots,k_0\), run the
\(O^*(1.708^k)\)-time polynomial-space decision algorithm of Červený and Suchý, and
return the first feasible \(k\). The total time is
\(O^*(1.708^{n/2}) = O(1.3069^n)\), polynomial space.

## Comparison

| Algorithm | Time | Space |
|---|---|---|
| Kardoš et al. 2011 | \(O^*(1.5171^n)\) | polynomial |
| Chang et al. | \(O^*(1.4658^n)\) | polynomial |
| Chang et al. 2018 | \(O^*(1.4613^n)\) | polynomial |
| Xiao–Kou 2017 | \(O^*(1.3659^n)\) | exponential |
| **This note** | \(\boldsymbol{O(1.3069^n)}\) | **polynomial** |

## Conditional improvements (2026 preprint)

Assuming the 2026 preprint of Gaspers (arXiv:2611.05146, Theorem C.3(a)), the following
conditional bounds are recorded:

- \(O(1.2823^n)\) polynomial space for all subcubic graphs, via a four-state Max 2-CSP
  encoding and elimination of degree-\(\le2\) variables;
- \(O(1.2812^n)\) polynomial space for triangle-free subcubic graphs, via a local
  branching analysis with measure \(\mu=0.95n_3+0.05n\);
- the \(1.2812\) bound is specific to triangle-free (or diamond/\(K_4\)-reducible)
  graphs; the general subcubic bound remains \(1.2823\).

These bounds are conditional on the preprint. The case analysis is a proof sketch, and
the encoding and diamond/\(K_4\) reductions have only been checked exhaustively on
small graphs.

## Files

- `note_1.3069.pdf` — compiled 5-page note.
- `note_1.3069.tex` — LaTeX source.

## Compile

```bash
pdflatex note_1.3069.tex
```

## Status and caveats

- The result is specific to graphs of maximum degree 3.
- It improves both the polynomial-space bound \(1.4613^n\) and the exponential-space
  bound \(1.3659^n\) for subcubic graphs.
- The lower bound is cited, not reproved here. The hybrid is elementary and may be
  folklore; a thorough novelty check has not been completed. Do not treat this as an
  established new record until the literature has been checked.
- The conditional \(1.2823^n\) and \(1.2812^n\) bounds depend on a 2026 preprint and
  are not part of the unconditional priority claim.
- The formal version of the parameterized algorithm is: R. Červený, O. Suchý,
  *Generating Faster Algorithms for d-Path Vertex Cover*, WG 2023, LNCS 14093,
  pp. 157–171.

## References

1. B. Brešar, F. Kardoš, J. Katrenič, G. Semanišin. Minimum \(k\)-path vertex cover.
   Discrete Applied Mathematics 159(12) (2011), 1189–1195.
2. F. Bock, J. Pardey, L. D. Penso, D. Rautenbach. A bound on the dissociation number.
   Journal of Graph Theory 103(4) (2023), 661–673.
3. R. Červený, O. Suchý. Generating faster algorithms for \(d\)-Path Vertex Cover.
   WG 2023, LNCS 14093, Springer, 2023, pp. 157–171. (Full version: arXiv:2111.05896.)
4. D. Tsur. Parameterized algorithm for 3-path vertex cover. arXiv:1809.02636, 2018.
5. M.-S. Chang, L.-H. Chen, L.-J. Hung, Y.-Z. Liu, P. Rossmanith, S. Sikdar.
   Moderately exponential time algorithms for the maximum bounded-degree-1 set problem.
   Discrete Applied Mathematics, 2018.
6. M. Xiao, S. Kou. Exact algorithms for the maximum dissociation set and minimum
   3-path vertex cover problems. Theoretical Computer Science 657 (2017), 86–97.
7. F. Kardoš, J. Katrenič, I. Schiermeyer. On computing the minimum 3-path vertex cover
   and dissociation number of graphs. Theoretical Computer Science 412 (2011),
   7009–7017.
8. S. Gaspers. Path decompositions of sparse graphs via Gaussian sweeps and faster
   exponential algorithms. arXiv:2611.05146, 2026.

## License

Text and figures: CC BY 4.0. LaTeX source: same.
