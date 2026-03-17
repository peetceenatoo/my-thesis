## Bilateral Trading under Budget Pressure

### A stronger benchmark

A theoretical study of online bilateral trade through the lens of regret minimization, aiming to provide an algorithm to compete against a **stronger distributional benchmark** under **global budget balance** in **stochastic environments**.

The goal is to compete with the best **distribution over price pairs** that remains budget balanced **in expectation** while maximizing expected gain from trade. This stronger benchmark captures the additional flexibility enabled by global budget balance and motivates the algorithmic design of the project.

At each round, a platform intermediates between a seller and a buyer with unknown private valuations. The learner posts prices and aims to maximize cumulative gain from trade (GFT) while ensuring global budget balance (GBB).

## Problem Setting

We consider a repeated interaction over a horizon $T$.

At each round $t$:
- A seller with valuation $s_t \in [0,1]$
- A buyer with valuation $b_t \in [0,1]$

The learner posts a pair of prices $(p_t, q_t)$:
- $p_t$ to the seller
- $q_t$ to the buyer

### Trade Condition

A trade occurs if both agents accept:
$\mathbb{1}\{s_t \le p_t\} \cdot \mathbb{1}\{q_t \le b_t\}$

### Objective

The learner aims to maximize cumulative gain from trade while enforcing global budget balance over the horizon.

## Benchmark

The performance is evaluated via **pseudo-regret** against a strong benchmark.

### Benchmark Definition

The benchmark is the best distribution over price pairs $(p, q) \in [0,1]^2$ that is **globally budget balanced in expectation** and maximizes expected gain from trade:
$\mathbb{E}_{(p,q) \sim \gamma}[\mathrm{GFT}(p,q)]$.

### Interpretation

- The learner competes against a **distributional policy**, not just a single fixed price.
- Prices $(p,q)$ may **violate budget balance at individual rounds**, as long as they satisfy it **in expectation**.
- This benchmark captures the possibility of occasionally incurring losses and compensating them with sufficiently profitable trades.

### Why This Benchmark?

- It **strictly generalizes** the classical *best fixed price* benchmark, since any fixed price can be viewed as a degenerate distribution.
- It is **strictly stronger**, because randomization enables better trade-offs between profit and gain from trade.
- It naturally reflects the flexibility introduced by **global budget balance**.
