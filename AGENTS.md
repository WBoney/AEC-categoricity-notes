# Instructions for research assistants (including ChatGPT Work)

This repository contains research-level notes on the OpenAI manuscript proving Shelah's eventual categoricity theorem. The notes are not an independently verified proof of the manuscript. The maintainer is a researcher in abstract elementary classes, model theory, set theory, and category theory.

## First actions in a new session

1. Read **[WORK_HANDOFF.md](WORK_HANDOFF.md)** for current decisions, open issues, and source numbering.
2. Read the current **[notes/main.tex](notes/main.tex)** directly from the repository (not a cached PDF), and check the relevant part of the original OpenAI manuscript supplied as `paper.pdf` in the **Abstract Elementary Classes** ChatGPT Project. If this Project file is not accessible in Work, request it or use an authorized copy; do not substitute another manuscript silently.
3. Inspect open pull requests, the main-branch HEAD, and recent GitHub Actions runs before editing. The November 12 consolidation includes the working-scheme revision, manuscript archive, reversal discussion, and descriptive PDF filename. Verify current states rather than relying on historical PR statuses.
4. Current reading material: the alternate working-scheme definition in `notes/working-scheme.tex` and its equivalence appendix in `notes/appendix-working-scheme.tex`. Read `review/working-scheme-changes.md` for changes, proof scope, and unresolved questions.

## Mathematical standards

- Distinguish in the notes and in conversation: **structural data/definitions**, **additional hypotheses**, **consequences proved from those hypotheses**, **results actually established in the manuscript**, and **our proposed reconstructions/generalizations**.
- Respect the manuscript's notation and result numbering; distinguish the source Section 5 from Section 4 of these notes.
- Never infer categoricity of a category of diagrams from categoricity of the underlying vertex AEC alone. Show where a diagram-level result is assumed or proved.
- Do not conflate an automorphism orbit at one eligible cardinal with a cross-cardinal diagram comparison. Preservation of orbit types under non-surjective designated arrows is a substantial requirement.
- Do not assume that any class closed under directed colimits with all ambient strong natural transformations is the intended `generated AEC`. The completion uses coherent systems of **designated smallest-level arrows**. The standard upward-completion theorem for an AEC in μ₀ supplies its AEC properties and recovers the small slice. The outstanding question is fullness of higher-level eligible arrows, not existence of that completion. Preserve the concrete coding and vocabulary-size hypotheses in the appendix.
- A finite-support term recipe can evaluate on arbitrary orders without proving the resulting structures are models in the AEC or eligible systems. Source Lemma 5.4 proves eligibility for padded orders under the package axioms.
- The general source calls maps *inside* a system "specified maps"; these need not explicitly be strong or even structural embeddings. Our functor-category account of `Diag_I(K)` is a categorical reformulation only where internal maps are structural embeddings. The later marked applications use strong internal maps.
- If a proof step is only suggested, call it a proposal/lemma to prove; do not turn it into an established statement.
- Check LaTeX theorem labels, cross-references, and syntax. Use `notes/references.bib`, preserving the source citations and numbering.

## Editing and publication

- Use the GitHub connector in Work for repository reads and writes. Create a topic branch and PR for substantive mathematical changes, then make commits scoped to specific changes. Do not overwrite or merge other PRs incidentally.
- The workflow compiles `notes/main.tex` on PRs, but **only main-branch pushes publish** to https://wboney.github.io/AEC-categoricity-notes/main.pdf. Verify the main build and deploy job succeeded before calling a PDF published.
- Avoid relying on ephemeral Actions artifact links as stable PDF URLs; direct artifact links have returned 404 in prior sessions.
- Do not silently merge a mathematical PR without the maintainer's authorization, except when the instruction to land the work is explicit. If edits are not merged, clearly say the published PDF does not contain them.
- Keep **WORK_HANDOFF.md** current when a milestone ends: math decisions, remaining questions, commit/PR status, next source location, and any unresolved verification.
- For exploratory mathematical discussion, avoid changing the notes without a request, but keep a concise proposal ready to incorporate when directed.

## Work-mode first message

"Continue the AEC categoricity reading project. Read AGENTS.md and WORK_HANDOFF.md in WBoney/AEC-categoricity-notes, inspect notes/main.tex and the original OpenAI manuscript paper.pdf in the Abstract Elementary Classes Project, verify PR/build status, and summarize current progress. Read the current alternate working-scheme definition and the equivalence appendix; preserve their explicit scope restrictions and the open higher-level fullness question. Distinguish structural data, new axioms, and derived results. Do not start editing until the relevant mathematical question has been discussed unless I ask for edits."
