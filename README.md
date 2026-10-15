# AEC categoricity notes

Working mathematical notes on the OpenAI manuscript proving Shelah's Eventual Categoricity Conjecture.

## Files
- [LaTeX notes](notes/main.tex)
- [Bibliography](notes/references.bib)
- [PDF build workflow](.github/workflows/build-pdf.yml)

## PDF
GitHub Actions compiles `notes/main.tex` on pushes to `main` and on pull requests. Open the latest successful [Build PDF workflow run](../../actions/workflows/build-pdf.yml) and download the `categoricity-notes-pdf` artifact. GitHub Actions artifacts are not permanent links and may expire.

## Editing
Use a branch and pull request for substantive changes to statements, definitions, and proofs. The LaTeX source is authoritative. The theorem-like environments share a numbering sequence by section. Citations to the original manuscript identify its result numbering.
