# AEC categoricity notes

Working mathematical notes on the OpenAI manuscript proving Shelah's Eventual Categoricity Conjecture.

## Files
- [LaTeX notes](notes/main.tex)
- [Bibliography](notes/references.bib)
- [PDF build workflow](.github/workflows/build-pdf.yml)

## PDF

Once GitHub Pages is configured to use **GitHub Actions** as its deployment source, the latest PDF is available at [Open latest PDF](https://wboney.github.io/AEC-categoricity-notes/main.pdf). This link updates whenever changes are merged to `main` and the build succeeds.

GitHub Actions compiles `notes/main.tex` on pushes to `main` and on pull requests. Open the latest successful [Build PDF workflow run](../../actions/workflows/build-pdf.yml) and download the `categoricity-notes-pdf` artifact. GitHub Actions artifacts are not permanent links and may expire.

## Editing
Use a branch and pull request for substantive changes to statements, definitions, and proofs. The LaTeX source is authoritative. The theorem-like environments share a numbering sequence by section. Citations to the original manuscript identify its result numbering.

## Research context and ChatGPT Work

- [Standing mathematical and editing instructions](AGENTS.md) — read before auditing proofs, editing LaTeX, or making GitHub changes.
- [Current research-state handoff](WORK_HANDOFF.md) — records our discussion through OpenAI manuscript Definition 5.2(3) and the next stopping point at Definition 5.2(4).

To continue in **ChatGPT Work**, start in the **Abstract Elementary Classes** ChatGPT Project if possible, open this repository with the GitHub connection, and instruct Work to read `AGENTS.md`, `WORK_HANDOFF.md`, `notes/main.tex`, and the original `paper.pdf` uploaded to that Project. Check any open pull requests and the latest PDF build. The repo files are the durable context; the original manuscript is the authority for what its statements claim. If Work cannot see the Project PDF, attach it to the new conversation rather than substituting a public paper.
