# The Product's Edge

**Live:** https://fractalyouniverse.org/Product_edge/ · Room VIII of [Fractal Youniverse](https://fractalyouniverse.org/)

Euler's product ζ(s) = ∏ₚ (1 − p^{−s})⁻¹ builds the zeta function from the primes — but only where there are no zeros. Where it converges it proves the zeros away; where the zeros live it never settles. Three live panels, computed in the browser from a prime sieve to one million:

1. **Where the product converges** — s = 2: the finite products over primes ≤ X close on π²/6 (error 1.1·10⁻⁷ at X = 10⁶).
2. **Where the product swings** — the critical line at the first ten zeros (each height re-verified on the page by |ζ(½ + iγ)| ≈ 0 from the alternating series; a control height t = 15 with |ζ| = 0.72 shows the swing is about the strip, not the zero): the finite products never converge and never stop; their logarithm follows the prime sum's rotating main term Re[X^{1−s}/((1−s) log X)].
3. **The compensated series** Σ (Λ(n) − 1) n^{−s}: partial sums settle to the right of the line (s = 0.9, 0.75, 0.6) and wander at and left of it (s = 0.5, 0.4).

**The theorem the page states (classical):** the abscissa of convergence of Σ (Λ(n) − 1) n^{−s} is exactly Θ, the supremum of the real parts of the zeros — so the Riemann Hypothesis holds if and only if the series converges for every Re s > ½. Building the Euler product to the right of the line is not a step toward RH; it is RH.

**Instruments, not proofs.** Every curve is a finite window; finite windows can refute and never prove. Nothing on this page bears on the truth of the Riemann Hypothesis.

## Receipts

The page recomputes every quoted value from its own sieve and compares with the Python twin:

```bash
python3 receipts/product_edge_receipts.py    # numpy; writes product_edge_receipts.json; asserts the ten zero heights via eta
python3 receipts/euler_product_check.py      # the first exhibits, including the amended expectation kept on display
```

Recorded on 2026-09-10 (Python, sieve to 10⁶, 78,498 primes): P_X(2) − π²/6 = −1.11·10⁻⁷ at X = 10⁶; |P_X(½ + iγ₁)| = 0.2147, 0.1152, 0.0611, 0.0228, 0.0131, 0.3204, 0.4174 for X = 10, 10², 10³, 10⁴, 10⁵, 3·10⁵, 10⁶ (a 32× swing); max |ζ(½ + iγ_k)| over k = 1..10 = 3.3·10⁻⁸; compensated partial sums at x = 10⁶: −1.1680 (s = 0.9), −1.1991 (0.75), −1.3111 (0.6), −1.6333 (0.5), −2.8705 (0.4).

An expectation corrected on the record: the first draft of the exhibit said the finite products at a zero "never come near 0"; they fell to 0.013 at X = 10⁵ before jumping to 0.42 at 10⁶. The right statement is *no convergence*, not *bounded away*.

## Files

- `index.html` — the instrument, self-contained (one external request: the font stylesheet; no analytics)
- `receipts/product_edge_receipts.py`, `receipts/product_edge_receipts.json` — Python twin and its output
- `receipts/euler_product_check.py` — the first exhibits

## Sources

- L. Euler, *Variae observationes circa series infinitas* (1737/1744, E72)
- H. von Koch, *Sur la distribution des nombres premiers*, Acta Math. 24 (1901) 159–182
- A. E. Ingham, *The Distribution of Prime Numbers*, Cambridge Tracts 30 (1932); H. L. Montgomery and R. C. Vaughan, *Multiplicative Number Theory I* (2007)
- S. M. Gonek, C. P. Hughes, J. P. Keating, *A hybrid Euler–Hadamard product for the Riemann zeta function*, Duke Math. J. 136 (2007) 507–549
- D. Platt, T. Trudgian, Bull. London Math. Soc. 53 (2021) 792–797
- A. M. Odlyzko, tables of zeros of the Riemann zeta function

Built 2026-09-10 by Travis Bergen with the Riemann agent.
