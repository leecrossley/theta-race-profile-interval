# A longer obstruction in the 547/727 prime race

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24411639.svg)](https://doi.org/10.5281/zenodo.24411639)

This result is now maintained in [theta-host-split-inert-race](https://github.com/leecrossley/theta-host-split-inert-race/tree/main/results/theta-race-profile-interval). This repository is archived and keeps its releases and DOI.

Assume the generalised Riemann hypothesis (GRH) for the primitive Dirichlet $L$-functions in the 547/727 race and its base field, including the Riemann zeta function. **The waiting factor $`C=2\exp(2.213003902943)=18.2862805781609\ldots`$ fails.** On the 547/727 field with $`b=r=2`$, there are arbitrarily large starting heights $`H`$ where no doubling that finishes by $`CH`$ loses more than $`1.9735\log 2`$. At other arbitrarily large heights the same deadline misses the gain. The earlier obstruction was $`2\exp(11/5)=18.05002699\ldots`$. [Theorem and proof](PROOF.md) [Earlier interval](https://github.com/leecrossley/theta-race-factor-18/blob/31ea5d495ca29f7f17869d1a3f321000266e4867/PROOF.md)

The certificate covers the closed log interval $`[1.008796429610,3.221800332553]`$. The limiting score stays above the loss threshold at **every** point. A check one trillionth beyond each end falls below the threshold. This determines the length of the connected interval containing the certificate to within $`2\times10^{-12}`$. A later calculation gives an interval of length $132/25$ elsewhere in the profile. The optimal factor remains open. [Longer interval](https://github.com/leecrossley/theta-race-distant-interval/blob/527fffe7b7808457b47a292144fea96b556158a8/README.md) [Numerical enclosures](evidence/check.txt)

The proof sums the infinite gamma correction in closed form using four evaluations of one elementary function. A second calculation integrates the original gamma term on the left, encloses it directly at the support boundary and uses positive trivial-zero terms on the right. Both verifiers use Arb for outward rounding. Uniform recurrence transfers the interval to arbitrarily large heights. The finite interval enclosures use direct computation. Transferring the profile to the prime score uses Alpöge's announced Dirichlet GRH theorem. It needs no independence assumption on the zero ordinates. [Closed formula](PROOF.md#sum-the-gamma-correction) [Independent verification of the global theorem](https://math.mit.edu/~drew/grh/) [Prior-work comparison](PRIOR-WORK.md)

## Replay

In a Python 3.10+ virtual environment run

```sh
python -m pip install -r requirements.txt
python closed_profile.py
python integral_check.py
python check_source.py
```

For the full replay on x86-64 Linux, run `bash verify-release.sh` with Git, curl, tar and zstd available. With Lean 4.33.1 on PATH and a built Git checkout of Mathlib at commit `0df444a360eaa60ab8c11dca51a86af692955474` with no local changes, run `bash verify-release.sh /path/to/mathlib4`. An optional second argument names a directory of the five upstream files listed in `check_source.py`. The script checks file hashes, repeats both numerical proofs, verifies the upstream records, compiles the three local Lean deductions and compares the result with the published receipt. [Lean statements](ProfileInterval.lean) · [File hashes](SHA256SUMS)
