# AEC Categoricity Reading Notes — Work Handoff

**Updated:** 2026-11-04  
**Next mathematical stopping point:** OpenAI manuscript Definition 5.2(4), the exhaustion criterion for arrows.

This file is a portable research-state record. New assistants should also read [AGENTS.md](AGENTS.md), the actual [notes/main.tex](notes/main.tex), the original **`paper.pdf`** attached to the **Abstract Elementary Classes** ChatGPT Project, and live GitHub PR/build status. Treat this as a summary of decisions, not a substitute for primary sources.

## Project scope and status

- Main aim: research-level reading of OpenAI's manuscript proving Shelah's Eventual Categoricity Conjecture, organized around different notions of type and the mechanisms used to compare them.
- This repository: https://github.com/WBoney/AEC-categoricity-notes
- Permanent PDF of **merged** main: https://wboney.github.io/AEC-categoricity-notes/main.pdf
- The detailed study of source Section 5, including Definition 5.2(1)--(3), is in **Section 4** of our `notes/main.tex`. The source's numbering and the notes' numbering are different.
- PR #14 (`functor-category-working-schemes`) merged on 2026-11-04: https://github.com/WBoney/AEC-categoricity-notes/pull/14 . This introduced the categorical reformulation and the first working-package notes. Additional clarifications to the mathematical notes are being incorporated with this handoff.
- PR #13 (a separate remark after source Theorem 3.11 about reversal/homogeneity): https://github.com/WBoney/AEC-categoricity-notes/pull/13 ; last observed open. Recheck before making assumptions.
- Main branch is authoritative after commits have been merged and the PDF deployment verified. Do not mistake an Actions PR artifact for a persistent main-branch PDF.

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

For a fixed scheme, choose eligible cardinals `S`, classes `C_mu` of structured diagrams (possibly marked) at each `mu in S`, designated arrows, a finite-support term recipe `F`, and proposed equivalence relations on bounded sorted tuples. In the unmarked case `C` may be seen as a non-full subcategory of `Diag_I(K)`. For marked objects `(D,a)`, use the faithful forgetful functor `U:C -> Diag_I(K)`; it need not be injective on objects or full.

**Distinguish raw data from additional axioms.** Existence of `U`, `F`, and comparison relations is data; satisfaction of source Definition 5.2(1)--(4) must be proved.

## Definition 5.2: conclusions from our discussion

### (1) Structural arrows and unions

- Arrows mean morphisms of `C`, not morphisms inside the index category. Each is componentwise strong after applying `U`, but additional arrow requirements can apply.
- All **isomorphisms of the structured systems** are arrows. For unmarked systems the forgetful functor is full on isomorphisms between eligible objects; marked systems must preserve marks.
- Coherence: if `X ⊆ Y ⊆ Z` and both inclusions into `Z` are designated arrows, so is `X -> Y`.
- Fixed-level Tarski–Vaught: nonempty increasing chains of `C_mu` inclusions whose total union has size `mu` have an eligible union with inclusion arrows; there is an additional common-upper-bound clause into an eligible object at `nu >= mu`.
- This is naturally compared with **Shelah's “AEC at mu”** terminology. It is not an ordinary all-cardinality AEC by itself. Chain closure for designated arrows, not merely the ambient diagram AEC, is what matters.

### (2a) Term template and presentations

- A well-order of **eligible size** is simply a well-order `L` with `|L|=mu in S`; "eligible well-order" is not a separate predicate.
- Every such `L` evaluates to `F(L) in C_mu`; embeddings between eligible well-orders give designated arrows (including mixed levels).
- Every eligible system at level `mu` is isomorphic, as a **structured** system, to **some** `F(L)` with `|L|=mu`. Thus eligible objects are precisely these EM-style presentations **up to isomorphism**, not necessarily all size-`mu` models of a larger background category.
- Finite-support terms can be evaluated for arbitrary orders as formal many-sorted structures, but that alone does not show the vertex structures lie in `K` or that the system is eligible. Source Lemma 5.4 proves eligibility of padded orders using union arguments. An expanded AEC with an honest all-order EM blueprint is a plausible alternative reconstruction, **not an established result from the stated working-package data**.

### (2b) Mixed downward Löwenheim–Skolem

If `nu <= mu` are eligible, every set of at most `nu` sorted occurrences in `X in C_mu` sits in an eligible `nu`-object included in `X` by a designated arrow (retaining any fixed marks).

Set `mu_0=min S` (the minimum exists for nonempty classes of cardinals). Combining (2b) with coherence shows that each eligible `X` is the directed union, in the **ambient diagram AEC**, of its designated `C_{mu_0}`-subobjects. Directedness: a pair of such subobjects has a union of size at most `mu_0`; apply (2b) and coherence to place them into a third.

**Background-AEC proposal (user's insight):** one could generate a class from `C_{mu_0}` by directed colimits of designated small-object arrows, then define strong embeddings using compatible/coherent decompositions into those arrows. Do **not** automatically inherit every ambient componentwise strong natural transformation—this forgets possible scheme-specific arrow conditions. This resembles an Ind-completion, but well-definedness with respect to chosen presentations, full AEC coherence, chain axioms, and LS remain to be checked. The manuscript does not assert this construction. The selected eligible EM objects need not exhaust all models at eligible sizes of any such generated AEC.

### (3) Types/diagrams

For each bounded sorted arity, the working scheme proposes an equivalence relation on tuples in eligible objects (possibly at different levels).

- **(3a) Invariance and type-like behavior:** respects atomic diagrams, restrictions, reindexings; **every designated arrow preserves comparisons**, including mixed-level arrows. This is a substantial extra axiom, not automatic for automorphism-orbit types.
- **(3b) Orbit characterization:** at any **fixed eligible level**, two tuples have equal working diagrams iff some structured isomorphism between their containing systems maps one to the other. Thus the same-level relation is exactly isomorphism-orbit equality. Cross-level comparisons remain extra data/hypotheses.
- The **empty tuple has exactly one diagram**. By (3b), this makes **all objects in `C_mu` isomorphic** at each eligible `mu`. This is *categoricity of the entire system*, much stronger than categoricity of the individual vertex AEC. Example: for pure sets and the walking-arrow shape, a bijective internal arrow and a proper inclusion give non-isomorphic diagrams even when all four vertices have the same size. In particular (2a) alone does **not** establish categoricity of the collection of `F(L)` for all well-orders of a given cardinality.
- Where this stronger system categoricity is actually established: source Proposition 5.6 single-model scheme; Theorem 8.6 marked increments; Theorem 9.3 finite marked iterations. Source Proposition 11.7 is **conditional on geometric-system categoricity**. Source Proposition 5.8 starts from categorical system schemes in reconstructing the diagram/type clause.
- **(3c) Uniform bound:** for each fixed bounded sorted arity, the number of types is bounded by a set independently of the eligible level. At fixed level these are empty-base automorphism orbits (apart from any named scheme data).
- **(3d) Realization/saturation:** a possible bounded joint diagram extending the diagram of an actual tuple must be realized over that actual tuple at the receiving level. With (2a), (2b), (3a), and (3b), a proof can be given by transporting a witness to the receiving level, using arrow preservation, then an isomorphism matching the base tuple. The source lists it explicitly.
- **(3e) Naturality on term tuples:** tuples whose term records have matching labels and **joint** order/equality patterns of supports have the same working diagram, even across levels. Proof for well-ordered charts: amalgamate index well-orders over the finite/bounded support pattern, enlarge to an eligible well-order, and use the induced **arrows** to carry both tuples to literally the same tuple. No nontrivial automorphism of the index well-order is needed. **At one eligible level**, (3b) then gives an automorphism of the entire eligible structured system mapping one such tuple to the other. That automorphism generally does **not** come from an automorphism of its indexing well-order. This is a consequence of the package axioms, not a new independent assumption for the simple well-order term-pattern form.

For a non-surjective arrow `h:X->Y` at a fixed eligible level, (3a)+(3b) imply that for every bounded tuple `a` there exists an **isomorphism** `f:X ~= Y` agreeing with `h` on `a`. This strong local homogeneity must be proved for the scheme. Do not silently assume any automorphism of `X` extends to `Y`.

## Next topic: Definition 5.2(4)

**Not yet discussed in depth.** Source (4) is an exhaustion criterion: compatible matches of bounded sorted lists, exhausting a source diagram, yield a designated arrow provided each vertex's nested small strong-submodel enumerations have strong images; additional scheme-specific arrow conditions must be proved separately. Do not treat this brief orientation as an agreed proof audit. The user wants to resume here.

## Publications and collaboration

- Work within the existing Abstract Elementary Classes ChatGPT Project if Work can access it, or attach the primary manuscript to a Work conversation if not.
- GitHub connector has worked in ordinary ChatGPT conversations; in Work, check it is connected/available, and read current source and PRs.
- Editing: topic branch -> scoped commits -> PR and LaTeX CI -> merge when explicitly authorized -> verify main PDF deployment. Do not suggest that PR artifacts are stable URLs: they have returned 404 before.
- At each session's end update the durable handoff with substantive decisions and outstanding proof obligations, so future assistant sessions do not need to reconstruct context from chat history alone.
