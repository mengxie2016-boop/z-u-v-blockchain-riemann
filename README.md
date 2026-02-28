# z-u-v-blockchain-riemann
z-u-v-blockchain-riemann: Z-U-V three-space dynamics with Riemann zeros for blockchain consensus. Each node gets unique γ. Three spaces: Z (chain/trust), U (state/reputation), V (anomaly/attack). f≈0.47454 from ln f+(π/2)f=0. f-Shrink ensures smooth control. 200 rounds: 201 blocks, 100/100 active, detects Sybil attacks via γ analysis.
# z-u-v-blockchain-riemann

Z-U-V three-space dynamics with Riemann zeros for blockchain consensus. Each node gets a unique Riemann zeta zero γ as genetic code. Three spaces: Z (chain/trust), U (state/reputation), V (anomaly/attack detection). Core constant f≈0.47454 from ln f+(π/2)f=0. f-Shrink operator ensures smooth, never-zero control. 200-round simulation: 201 blocks produced, 100/100 active nodes, detects Sybil attacks via γ distribution analysis (7/15 anomaly bins with 20 fake nodes).

## Mathematical Foundation

**Core Constant**: ln f + (π/2)f = 0 → f = (2/π)·W₀(π/2) ≈ 0.4745409995126511

**f-Shrink Operator**: ℱ(x) = sgn(x)·√|x|·f^{|x|/(2f)}

**Z-U-V Triple Duality**:
- Z-space: z_{n+1} = (z_n + e^{-πz_n/2})/2 → converges to f
- U-space: u_{n+1} = √u_n·e^{-πu_n/4} → converges to f
- V-space: v = e^{πz/2} = 1/u → converges to 1/f

## Riemann Zero Encoding

Each node gets a unique Riemann zero γ (first 100: 14.134725 to 216.281319), normalized to [0.5, 2.5]:

| Space | Parameter | Modulation |
|-------|-----------|------------|
| Z | Trust/Stake | r_z = 0.3 + 0.4·γ, stake = 100·(0.5+0.5·γ) |
| U | Reputation | η_u = 0.7 + 0.3·γ |
| V | Attack threshold | θ_v = 0.15·γ |

## System Architecture

- **Node Class**: Maintains Z (trust, blocks), U (reputation, energy, LTP), V (trust score, isolation)
- **Consensus**: Reputation-weighted voting, dynamic block sizing (3+5·γ transactions)
- **Attack Detection**: γ distribution monitoring, temporal anomaly detection, auto-isolation at trust < 0.1

## Results (200 rounds)

Final chain height: 201 blocks
Total proposals: 5205
Active nodes: 100/100
Isolated nodes: 0
Avg trust: 0.851
Avg reputation: 1.008

## Attack Simulation (20 fake nodes)

Anomaly bins: 7/15
Fake nodes detected: 20
Active nodes after: 120 (all detected but not auto-isolated due to conservative threshold)

## Key Features

- **Z-space**: Dynamic block sizing, stake-weighted voting, difficulty adjustment
- **U-space**: Space-specific learning rates, reward/penalty mechanism, long-term reputation
- **V-space**: γ distribution monitoring, temporal anomaly detection (std > 2.0), auto-isolation
- **f-Shrink**: Adaptive beta per space, overflow protection, never-zero property

## Requirements

numpy, matplotlib, networkx, IPython

## Run

python blockchain_simulation.py

## Papers

Xie, M. (2026). Global Dynamics of a Transcendental Iteration System Based on the Balance Equation. Zenodo. https://doi.org/10.5281/zenodo.18485110

Xie, M. (2026). f-Shrink: A Self-Adaptive Contraction Operator Derived from Transcendental Dynamics and Its Applications in Deep Learning. Zenodo. https://doi.org/10.5281/zenodo.18694170

Xie, M. (2026). From Two Iterative Formulas to the Global Structure of the Riemann Hypothesis: The Z-U-V Triple Duality. Zenodo. https://doi.org/10.5281/zenodo.18767100

---

**Built on pure math: one constant f, one operator ℱ, infinite zeros γ, three spaces Z-U-V.**
