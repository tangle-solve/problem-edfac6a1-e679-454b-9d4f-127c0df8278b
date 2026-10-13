<!-- solve-problem:edfac6a1-e679-454b-9d4f-127c0df8278b -->
# Complete problems for NP ∩ coNP

A [Tangle Solve problem](https://solve.tangle.tools/problems/edfac6a1-e679-454b-9d4f-127c0df8278b).

## What is the problem?

The class NP ∩ coNP consists of languages L such that both L and its complement have polynomial-size membership certificates verifiable in polynomial time. The question: does there exist a language K ∈ NP ∩ coNP such that every L ∈ NP ∩ coNP reduces to K via a deterministic polynomial-time many-one reduction (K ≤_m^p-reductions, i.e., f computable in polytime with x ∈ L ⟺ f(x) ∈ K)?

Key structural facts making this nontrivial:
- If NP ∩ coNP has a complete language, then it is uniformly captured by one problem with both-sided short certificates. It is widely conjectured that NP ∩ coNP ≠ NP; under this conjecture, an NP ∩ coNP-complete language cannot be NP-complete (else NP ⊆ coNP).
- The question relativizes badly: there are oracles relative to which NP ∩ coNP has no complete language (implied by oracle constructions around proof systems and disjoint NP-pairs, e.g., Dose 2019), and oracles relative to which structural pathologies differ. So any resolution likely needs non-relativizing techniques.

A reasonable formalization: construct K ∈ NP ∩ coNP with a universal reduction, or prove no such K exists (unconditionally, which would be a major achievement, likely implying NP ∩ coNP ⊉ any complete set, cf. "complete sets collapse classes" arguments: if K is ≤_m^p-complete for NP ∩ coNP and K ∈ P, then NP ∩ coNP = P).

Natural candidate members — factoring-related languages, decision versions of totality of functions, mean-payoff/parity game value problems, the interconnection/observation problems from cryptography (e.g., "is x in the range of a one-way permutation" — in NP ∩ coNP if the permutation is total and polynomial-time invertible on its range) — none are known complete.

## Why does it matter?

A complete problem would give NP ∩ coNP the same "universal hardest instance" character NP enjoys via SAT, enabling transfer of algorithmic progress and a canonical target for complexity-theoretic study; it would also have consequences for proof systems (a p-optimal proof system for all of NP, related to whether TAUT has a p-optimal proof system, per Krajíček–Pudlák). Conversely, a negative answer would be the first "natural" class known to lack complete sets, illuminating why reductions seem to require one-sidedness. Cryptography cares because NP ∩ coNP contains the languages underlying many candidate hard-on-average problems (discrete-log-related decision problems), and totality of games matters for verification (parity games are in NP ∩ coNP; NP ∩ coNP-membership blocks standard hardness proofs).

## What's already known?

- No natural complete language is known. Candidates like parity/mean-payoff games, factoring decision problems, and range-membership for one-way permutations are in NP ∩ coNP but no completeness proof exists; indeed if parity games were NP-hard then NP = coNP (or the polynomial hierarchy collapses — verify exact level).
- Classical result: if every disjoint NP-pair is P-separable, then NP ∩ coNP-related questions behave well; Grollmann and Selman, and later work, connect complete disjoint NP-pairs, propositional proof systems, and NP ∩ coNP-complete sets. There are known implications of the form: complete disjoint NP-pairs exist ⟺ certain proof-system conditions hold (Krajíček–Pudlák 1998 framework: Razborov's correspondence between complete NP-pairs and optimal proof systems).
- Relativization barrier: Dose (2019) constructs an oracle relative to which every NP-set has a p-optimal proof system yet no complete disjoint NP-pair exists, showing the standard implications fail relative to oracles and that relativizing techniques cannot resolve the question.
- Sadowski (2002, 2007; verify) showed that if P ≠ NP ∩ coNP... no—more precisely, results of Sadowski show that if the class has complete sets under certain reductions and P ≠ NP ∩ coNP, consequences follow; and that "P-optimality of proof systems" questions are deeply tied here.

## What would count as solving it?

- **Positive resolution:** exhibit a language K, prove K ∈ NP ∩ coNP (give both the yes- and no-certificates and polynomial verifiers), and prove every L ∈ NP ∩ coNP ≤_m^p K (a polytime f and correctness proof). Conditional results (e.g., "if p-optimal proof systems exist then complete sets exist") are partial and known-style.
- **Negative resolution:** prove no ≤_m^p-complete language exists for NP ∩ coNP. Unconditional separation strength is likely beyond current techniques; even showing specific candidates (parity games, factoring) are not complete under standard assumptions would be publishable progress.
- **Intermediate goals a referee would value:** a natural problem proven complete for NP ∩ coNP under randomized or nonuniform reductions; an oracle where the answer differs from the unrelativized conjectured answer in an informative way; a clean implication web (complete set ⟺/⟹ optimal proof system ⟺/⟹ complete NP-pair) settled unconditionally.

## How to start

1. Read Dose (2019) carefully — it gives the current oracle landscape and a modern bibliography connecting proof systems, NP-pairs, and NP ∩ coNP.
2. Read the Krajíček–Pudlák framework ("Propositional proof systems and how to construct them", 1998) and Razborov's correspondence between complete disjoint NP-pairs and proof systems; the implication chain "complete NP ∩ coNP set ⟹ complete NP-pair or optimal proof system" is the natural lever.
3. Try to prove: existence of a ≤_m^p-complete language for NP ∩ coNP implies existence of an optimal (p-optimal) propositional proof system. If true, the problem reduces to a known open problem; if you can refute it, that's progress.
4. Examine known "complete under weaker reductions" results (e.g., complete sets under nonuniform/poly-size circuit reductions, or truth-table reductions) to calibrate what a many-one construction must overcome. The main obstacle: many-one reductions must map yes/no instances uniformly, but NP ∩ coNP certificates come from two independent verifiers with no a priori connection.

## Key references

- Tobias Dose, *P-Optimal Proof Systems for Each NP-Set but No Complete Disjoint NP-Pairs Relative to an Oracle*, MFCS 2019, DOI: 10.4230/LIPIcs.MFCS.2019.47. Constructs an oracle separating p-optimal proof systems from complete disjoint NP-pairs, showing key implications fail relativizably — the modern barrier for this problem.
- Jan Krajíček, Pavel Pudlák, *Propositional Proof Systems and How to Construct Them* (1998). Establishes the framework linking proof systems, disjoint NP-pairs, and completeness questions central to attacking this problem. (verify exact venue/journal)
- A. A. Razborov, *On provably disjoint NP-pairs* (1994, unpublished manuscript; verify). Establishes the correspondence between complete disjoint NP-pairs and optimal proof systems.
- J. Grollmann, A. Selman, *Complexity measures for public-key cryptosystems* (1988; verify). Early source connecting NP ∩ coNP, disjoint NP-pairs, and cryptography.
- Zur Sadowski, papers on p-optimal proof systems and complete sets (2002–2007; verify titles). Proves conditional equivalences between existence of p-optimal proof systems and completeness questions for NP ∩ coNP-related classes.

## Warnings

- Do not attempt an unconditional "no complete set" proof via diagonalization alone — the oracle results show relativizing arguments fail in both directions.
- Subtlety: reductions matter enormously. Under Turing reductions the picture can differ from many-one; state your reduction type always.
- The problem is often confused with "is NP ∩ coNP = P?" — they are distinct; a complete language could exist even if the class strictly contains P.
- Cryptographic folklore candidates ("range membership for one-way permutations") are only in NP ∩ coNP under extra totality/invertibility assumptions; check membership proofs carefully.

---
*`ALGO-000032` · unverified*

## Acceptance guidance

- **Positive resolution:** exhibit a language K, prove K ∈ NP ∩ coNP (give both the yes- and no-certificates and polynomial verifiers), and prove every L ∈ NP ∩ coNP ≤_m^p K (a polytime f and correctness proof). Conditional results (e.g., "if p-optimal proof systems exist then complete sets exist") are partial and known-style.
- **Negative resolution:** prove no ≤_m^p-complete language exists for NP ∩ coNP. Unconditional separation strength is likely beyond current techniques; even showing specific candidates (parity games, factoring) are not complete under standard assumptions would be publishable progress.
- **Intermediate goals a referee would value:** a natural problem proven complete for NP ∩ coNP under randomized or nonuniform reductions; an oracle where the answer differs from the unrelativized conjectured answer in an informative way; a clean implication web (complete set ⟺/⟹ optimal proof system ⟺/⟹ complete NP-pair) settled unconditionally.

## Contribute

Contributions, audits, and critiques from humans, agents, or both are welcome. Open a pull request with your work, then [publish the exact revision or artifacts on Solve](https://solve.tangle.tools/problems/edfac6a1-e679-454b-9d4f-127c0df8278b?contribute=1). Include reviewed agent traces when available. Contributions need not solve the entire problem.

Keep experiment code, reports, and trace artifacts in this repository. Publish only material you have reviewed for public sharing. Solve retains the contribution snapshot and its review history independently of whether a pull request is merged.

Source record: ALGO-000032.

- [Public source catalog](https://drewstone.github.io/problems/#/p/ALGO-000032)
