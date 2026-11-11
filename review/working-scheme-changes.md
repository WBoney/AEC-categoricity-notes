# Working-scheme integration: review record

Date: 2026-11-11. This is a review proposal, not a merged change.

## Inputs checked

- Notes main: `b640a66dd3a3c8957aa3df84308aee83cbdd6f2c`.
- Boney's current `WBoney/ReworkingOpenAI/main.tex`: Git blob `572b915cd0a8f73b0f8b5713e8c256715215576c`.
- Original OpenAI manuscript, September 24, 2026 directory, Definition 5.2 and Convention 5.1, printed pp. 29–30. Downloaded PDF blob: `f743110d3c1faeca9a28b8f741e401cef319ca68`, matching the archived copy in still-open PR #16.
- Jarden–Shelah, *Non-forking frames in abstract elementary classes*, Definition 1.0.16 and Fact 1.0.18 (citing Shelah II, Lemma 1.23): the standard upward-completion theorem.
- Before editing, PRs #10, #13, #16 were open. Main remained at the SHA above; main run 41932160564 and archive-branch run 42263481874 were successful. No other PR is changed or merged.

## Organization

Section 4 now uses the alternate definition, with lifted automorphism comparison defined globally before its axioms. It distinguishes the generated AEC, eligible objects, and designated morphisms. The prior duplicated package/read-through is replaced by a focused definition, consequences, and warnings. Earlier Sections 1–3 are preserved mathematically.

Appendix A restates source Definition 5.2 with its four clause numbers retained as S1–S4, then proves the translations. The source definition is a restatement, not a verbatim quotation. The equivalence theorem states its coding and cofinality scope explicitly.

## Mathematical changes to the alternate draft

1. **“AEC over” is now concrete.** It uses the same sorted carriers, structural language, maps, and unions. Its forgetful functor is faithful and preserves directed colimits; no fullness is assumed. Abstract faithfulness alone would not identify underlying sets, isomorphisms, or size.
2. **Minimum-size normalization is explicit.** The language has size at most μ₀, μ₀ ≥ LS(K), and K^gen has no models below μ₀. We use a nonempty finite system shape, so its total size is its vertex level. The source does not explicitly give all these bounds at its original minimum. Passing to a tail is possible but changes the levels. This is an actual qualification of the equivalence, not a claim that the source states the normalization.
3. **The template is precisely a system-code recipe.** Its finite-support semantics evaluate equality, all system symbols, and names. The EM notation does not name an extra skeleton. This avoids changing structured automorphism groups. Membership is required only on eligible well-orders, not all linear orders.
4. **Internal-map scope is explicit.** The diagram formulation requires internal structural embeddings. A parallel formulation with arbitrary specified internal functions covers the source's more general wording. It uses the same proofs, but a different ambient category.
5. **Small slice equality includes morphisms.** `(C_{μ₀},H_{μ₀}) = K^gen_{μ₀}` is preserved exactly. The standard upward-completion theorem corrects the older notes' claim that all completion axioms were unproved.
6. **The axiom list is shortened by proofs.** Mixed-arrow factorization, eligible categoricity, term naturality, and realization remain in the notes as consequences, rather than independent axioms. The uniform set bound is also proved. No intended requirement from those clauses is discarded.
7. **Mixed-arrow factorization uses the entire family (H_μ).** The proof uses support suborders and coherence, and includes the converse by composition. It does not show that H_{μ₀} determines all higher H_μ.
8. **Lifted types stay primary.** Their equivalence (especially transitivity) and the full same-level orbit biconditional are axioms. Source D-equality is proved to equal the lifted comparison. Condition (*) follows for arbitrary chosen common-target arrows and is not added separately.
9. **Bounds and enumerations are explicit.** All type comparisons use the same sorted index pattern, bounded at both levels. Joint realization bounds the full joint tuple. Set notation in exhaustion is replaced by shared sorted enumerations; small vertex submodels must be contained in the matched sets.
10. **Closure uses nonempty inclusion chains.** The common-upper-bound clause permits a larger eligible target. A lemma proves that chains of length <μ⁺ suffice for all fixed-level chains whose union still has size μ.
11. **Countable exhaustion gains a proof of its scope.** At cf(μ)=ω, every ordinal-indexed increasing bounded-set exhaustion has a countable cofinal subchain. Thus countable exhaustion covers the nested ordinal version at these levels. Arbitrary directed families and preliminary levels of other cofinalities are not covered by that lemma.
12. **The partial-map formulation is reconciled with the total-map draft.** Atomic agreement makes compatible partial matches assemble to a structural embedding. Nested strong images give component strongness; membership in H still uses exhaustion, including any additional geometric obligation.

## Typographical and notational repairs

- The draft's displayed `P_κ(A)` tested `|A|<κ` instead of `|A₀|<κ`. The integrated text avoids the abbreviation and states the subset size directly.
- Fixed the curly prime in μ′, unclosed parentheses, “vertext,” and “types as the equivalence relation” (now equivalence classes).
- Distinguished the finite shape I from indexing well-orders L, and used τ^gen consistently for the system code rather than the earlier single-model EM macro.
- Qualified the unique-empty-type explanation: its uniqueness follows from common targets, and system categoricity then uses the orbit axiom.

- Fixed pre-existing title/ledger commands (`\\large` and `\\midrule` lacked the command backslash after the line break), wrapped an oversized implication display without changing it, rephrased one unbreakable compound, and enabled URL line breaks for the bibliography.

## What is proved, and what remains for review

The two directions are proved for concretely coded systems satisfying the stated minimum-cardinality normalization, at the source's countable-cofinality levels (or with matching countable exhaustion conventions). The upward-completion theorem is cited as standard; the application to eligible objects and arrows is proved here.

Remaining questions are not hidden inside “equivalence”:

- Whether higher-level designated arrows are all generated strong embeddings is unresolved and unnecessary for the equivalence.
- To claim the literal full source definition at an unnormalized original minimum, one must address the vocabulary/LS bounds there.
- To cover non-structural specified internal maps, use the explicitly described general system category instead of Diag_I(K).
- At preliminary levels of other cofinalities, choose and verify the desired exhaustion convention on both sides.
- No all-linear-order membership theorem for the template, general amalgamation theorem for K^gen, or identification with its Galois types is asserted.

## Validation

- Local `latexmk -pdf -interaction=nonstopmode -halt-on-error` completed successfully: 35 pages.
- Final LaTeX log has no warnings, undefined references/citations, or overfull boxes.
- Label audit found no missing or duplicate labels; `git diff --check` passed.
- Visually reviewed the rendered new definition, proofs, warnings, appendix, and bibliography (pp. 25–35).
- Review snapshot: `review/working-scheme-review.pdf`. The alternate definition begins on p. 25; the appendix starts on p. 30; the equivalence theorem is Theorem A.12 on p. 34.
- This PDF is a branch review snapshot, not the deployed main PDF. GitHub CI status is available on the review PR.
- The local TeX installation lacked its generated format and font-map caches; those were reconstructed in temporary storage. No environment workaround was added to the repository or its CI configuration.
