# AEC Categoricity Reading Notes — Work Handoff

**Updated:** 2026-11-11. **Status:** draft [PR #17](https://github.com/WBoney/AEC-categoricity-notes/pull/17), branch `working-scheme-alternate-definition`; not merged.

Local validation: 35-page PDF compiled with no warnings or missing references; new pages visually inspected. Review snapshot: `review/working-scheme-review.pdf`. Definition pp. 25–28; Appendix A pp. 30–35; equivalence Theorem A.12 p. 34.

## Current task and authoritative files

The user requested incorporation of the alternate definition from `WBoney/ReworkingOpenAI`, an appendix restating source Definition 5.2 and proving equivalence, and a complete review record of fixes and problems. This authorizes the topic branch and PR; it does **not** authorize merging.

Read `AGENTS.md`, `notes/main.tex`, its new inputs `notes/working-scheme.tex` and `notes/appendix-working-scheme.tex`, and `review/working-scheme-changes.md`. The latter records input SHAs, changes, scope, and validation. Source Section 5 remains distinct from notes Section 4 and Appendix A.

Original manuscript: https://github.com/openai/math/blob/main/preprints/Eventual-Categoricity-for-Abstract-Elementary-Classes-September-24-2026/paper.pdf . Read the original directly; shell raw download works if the connector cannot return a binary. Its Git blob is `f743110d3c1faeca9a28b8f741e401cef319ca68`. PR #16 archives the same bytes and is still open.

Before this edit, main was `b640a66dd3a3c8957aa3df84308aee83cbdd6f2c`, PRs #10/#13/#16 were open, and latest main run 41932160564 succeeded. These are historical checks: recheck when needed. The published main PDF at https://wboney.github.io/AEC-categoricity-notes/main.pdf does not contain this unmerged review.

## Mathematical decisions now reflected in the review

- Lifted automorphism comparison is primary: eligible common target, designated maps, structured automorphism. Its equivalence and full same-level orbit biconditional are axioms. It is proved to equal source D, so D is not a free choice once a package exists.
- Mixed downward closure, categoricity, uniform type bound, joint realization, term naturality, and factorization of mixed arrows are proved consequences. Condition (*) follows for any chosen common-target arrows.
- The generated AEC is the standard upward completion of the AEC in μ₀ with its designated arrows. Jarden–Shelah Definition 1.0.16 and Fact 1.0.18 cite Shelah II Lemma 1.23. This corrects the old handoff: the completion's AEC axioms are not all unresolved.
- Small designated subobjects form a μ₀⁺-directed cover of every eligible object. Original arrows belong to the completion. Equality of higher-level H with all generated strong embeddings remains unresolved; it is neither needed nor claimed in the equivalence.
- All fixed-level H_μ, together with order-presentation arrows, determine the mixed arrows. This is not a claim that H_{μ₀} alone recovers all higher H_μ.
- Exhaustion uses actual compatible bounded sorted matches. Vertex resolutions are additional nested strong-model witnesses **inside** the matched lists. Component strongness follows by AEC unions; a geometric condition still needs its own verification when proving exhaustion for a scheme.
- New proved observation: at cf(μ)=ω, every ordinal-indexed nested exhaustion by sets of size <μ has a countable cofinal subchain. The prior indexing concern is resolved in this scope, not for directed families or preliminary levels of other cofinalities.

## Equivalence theorem: precise scope and remaining questions

The appendix proves both directions for the same concrete sorted system code, vocabulary size ≤μ₀, μ₀≥LS(K), and the countable-cofinality exhaustion regime. The AEC-over convention preserves carriers, maps and unions, not just abstract faithfulness.

The diagram version presupposes internal structural embeddings. The source's potentially arbitrary specified maps require the explicitly described general system category. The source does not explicitly state all minimum-language bounds; restricting to a suitable tail changes preliminary levels and is not silently an exact equivalence there.

The finite-support recipe is not an all-order AEC blueprint. No skeleton is silently added to the structured automorphism language. Formal arbitrary-order structures need not belong to K^gen or be eligible. The other continuing themes are reversal beyond unbounded categoricity, placed diagrams and Galois types after selected-level amalgamation, multidimensional independence/excellence, and translation of the later geometry.

## Established organization of earlier reading

The notes were reorganized into a "types of types" discussion. Important comparisons include:
- Order skeleton/term records and their support patterns (`tp`, `tp^*` in the expanded ordered class).
- Automorphism-orbit types, including the EM-lifted variant, and source Theorem 3.5 on homogeneity of special orders.
- Arrow-type relations, eventual reversal (Theorem 3.11), stabilization, and canonical diagrams.
- Galois types and EM-lifted Galois types; comparison of automorphism, arrow and Galois types, and placed/natural diagrams. Distinguish equality, one-way implication and eventual equivalence.
- Locality/compactness-like consequences and later finite-system constructions.

The new focus is the abstract framework of source Section 5, not a new formalization of AECs in Lean. Other projects (e.g. Lean formalization of a compactness result) should not be folded into this reading project.

## Category-theoretic formulation of working systems

Fix an AEC `K` as a category of models with strong embeddings. Define `K^{*tau}` to have the same objects but all **structural tau-embeddings** as morphisms.

For a fixed finitely generated small category `I` (possibly infinitely many morphisms, at most countably many; not necessarily finitely presented), distinguish:

1. `Fun(I,K)`: internal maps are strong embeddings; natural transformations are componentwise strong.
2. `Diag_I(K)`: objects are functors `I -> K^{*tau}`; arrows are componentwise strong natural transformations.
3. `Fun(I,K^{*tau})`: internal maps and transformation components may be only structural embeddings.

We have `Fun(I,K) ⊆ Diag_I(K) ⊆ Fun(I,K^{*tau})`; the first inclusion is full and the second generally is not. The sorted diagram classes in (1) and (2) satisfy the ordinary AEC axioms using componentwise strong subfunctors. Their LS bound is at most `max(LS(K), |Mor(I)|, aleph_0)`, hence at most `LS(K)` for finitely generated `I`.

The source speaks of finite *systems* with specified internal maps and external componentwise strong arrows. It does not explicitly assert that every internal specified map is structural, so the functor formulation is a **reformulation with a scope caveat**, not an exact claim about the full generality of the manuscript. Later marked systems use strong internal maps.

A global class `Diag(K)` can be regarded as pairs `(I,D)` ranging over finitely generated shapes `I`; `mu-Diag(K)` selects those with every vertex sort of size `mu`. **A particular working scheme fixes the shape `I`**, so the working objects sit within one such fiber.

A many-sorted language `tau_I` has one sort for each **object of I** (not for the possibly overlapping image sets), a copy of `tau(K)` on each sort, and names for internal maps. Sorted tuples record their sort patterns.

For a fixed scheme, choose eligible cardinals `S`, classes `C_mu` of structured diagrams (possibly marked) at each `mu in S`, designated arrows, a finite-support term recipe `F`, and lifted automorphism comparisons on bounded sorted tuples. In the unmarked case `C` may be seen as a non-full subcategory of `Diag_I(K)`. For marked objects `(D,a)`, use the faithful forgetful functor `U:C -> Diag_I(K)`; it need not be injective on objects or full.

**Distinguish raw data from additional axioms.** The concrete `U`, finite-support recipe, and selected arrows are data; equivalence, the orbit axiom, and exhaustion must be established. See the new definition and appendix for the complete axioms.


## Publication workflow

Use the GitHub connector for writes, a topic branch, scoped commits, and a review PR. Do not merge until explicitly requested. Verify LaTeX CI. Only main pushes deploy the published PDF; PR artifacts are not durable main-PDF links. Update this handoff at each substantive milestone, preserving uncertainties rather than turning proposals into theorems.
