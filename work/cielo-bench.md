# cielo-bench

> Check or agree? When an AI agent can verify a user’s claim with a tool, does it check it, or does it agree anyway? An open benchmark with deterministic scoring and no LLM judge.

Canonical page: https://vvanegasar.github.io/work/cielo-bench/
Author: Valentina Vanegas Aristizábal (Head of AI & Technology)

*Research · Open source · v1.0, the instrument*

Check or agree? When an AI agent can verify a user’s claim with a tool, does it check it, or does it agree anyway? An open benchmark with deterministic scoring and no LLM judge.

- Status: Built and validated with simulated agents · Real-model results pending
- Role: Author. I specify, direct and validate; implementation is agent-assisted.
- Ground truth: NASA/JPL Horizons ephemerides; a synthetic company database
- Stack: Python, MCP (stdio, Streamable HTTP), SQLite
- License: MIT

## Abstract

cielo-bench measures sycophancy in tool-using AI agents against verifiable ground truth. Each question is asked with a true and with a false user premise, at three levels of user pressure, with and without a tool that can check it, and with the tool’s source failing. Answers are scored deterministically, without an LLM judge.

## 1. Why

An agent that accepts a false premise when it cannot check is ignorant. An agent that accepts it *after its own tool returned the contrary evidence* is agreeing with the user, not with the facts.

> Note 1: This is the distinction the benchmark is built to measure. Most evaluations ask another model to grade the answer; here the ground truth is computed, so an answer is within tolerance or it isn’t.

cielo-bench separates the two:

- it asks **the same item with and without** the verifying tool;
- it uses a **true and a false** user premise;
- it applies three levels of **user pressure**;
- it makes the **source fail**, to see whether the agent admits it or invents an answer.

## 2. Design

Figure 1. The design. The same item runs in three conditions; the tool answers from a frozen, hashed copy of the ground truth, and the failing source returns `source_unavailable` with no values.

Table 1. Factors and levels.

| Factor | Levels |
| --- | --- |
| Tool | `no_tool`, `tool` (answers from the frozen ground truth) |
| Premise | true, false (same wording, same pressure frame) |
| Pressure | neutral (“Is it true that…?”), assertive (“I’m certain that…”), authority (“I’m a professional astronomer and I’m certain that…”) |
| Faults | `fault_down`, `fault_error`, `fault_empty`: the tool returns `source_unavailable` and no values |

## 3. The metric

Let *F* be the false-premise trials and *E* ⊆ *F* those in which a tool returned evidence that contradicts the premise.

> Note 2: Also reported, each with k/n, a Wilson 95% interval and a cluster-bootstrap 95% interval over templates: verification rate, user correction, verdict and value accuracy, honest refusal and hallucination under faults, cost and latency.

agree-after-check = |{ t ∈ E : the final verdict agrees with the user }| / |E|

Paired contrasts (tool − no tool, pressure effects, faults) use McNemar exact tests with Holm adjustment over a pre-specified family.

## 4. The instrument

Two domains plug into one interface: 270 premise pairs in all. These numbers are properties of the benchmark, not results.

Table 2. Golden sets, v1.

| Domain | Ground truth | Pairs | Templates | Languages | SHA-256 |
| --- | --- | --- | --- | --- | --- |
| astronomy | JPL Horizons, seen from Medellín, Bogotá and Barranquilla | 144 | 18 | EN 72 · ES 72 | `418b7670…` |
| tabular | Read-only SQL on a synthetic distributor | 126 | 7 | EN 63 · ES 63 | `19ecd576…` |

Every fact is re-derivable offline from hashed fixtures, and every report records the commit, the golden-set hash, the model versions, the design, the prices and the run date.

## 5. Results

Pending: Results with real models will appear here after the first complete run. No numbers are shown until then; each will carry k/n, its 95% intervals, the commit and the golden-set hash.

## Links

- [Code](https://github.com/vvanegasar/cielo-bench)
- [DOI (Zenodo)](https://doi.org/10.5281/zenodo.24441942)
- [Method](https://github.com/vvanegasar/cielo-bench/blob/main/docs/EVALS.md)
- [Cite](https://vvanegasar.github.io/work/cielo-bench/#cite)

## Cite

```bibtex
@software{vanegas_aristizabal_cielo_bench,
  author  = {Vanegas Aristizábal, Valentina},
  title   = {cielo-bench: Check or agree? A benchmark of whether
             tool-using AI agents verify a user's claim or agree with it},
  version = {1.0.0},
  license = {MIT},
  doi     = {10.5281/zenodo.24441942},
  url     = {https://doi.org/10.5281/zenodo.24441942}
}
```

Credits: Ephemerides: NASA/JPL Solar System Dynamics, Horizons. The tabular data is synthetic. Not endorsed by NASA or JPL.

## Contact

- Email: aristizabal56vane@gmail.com
- LinkedIn: https://www.linkedin.com/in/vvanegasa
- GitHub: https://github.com/vvanegasar
- Contact form: https://vvanegasar.github.io/contact/
