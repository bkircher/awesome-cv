# Repository Guidelines

## Project Structure & Module Organization

The core class lives in `awesome-cv.cls`. Example documents and their section
snippets are under `examples/`, with `resume/` and `cv/` directories holding
modular content blocks. Keep new sample documents alongside the existing `.tex`
wrappers so `Makefile` targets pick them up automatically. Preview assets
(`.png`, `.pdf`) belong in the same directory as their source to keep diff noise
contained.

## Build, Test, and Development Commands

- `make examples` builds the resume, CV, and cover letter PDFs in `examples/`
  using `xelatex`.
- `make clean` removes generated PDFs so you can produce a fresh run or
  regenerate screenshots.
- `xelatex -output-directory=examples path/to/doc.tex` compiles a single
  document when iterating on a new layout.

## Coding Style & Naming Conventions

- Use two-space indentation inside environments and keep closing braces on their
  own line, matching the style in `examples/resume.tex`.
- Name new LaTeX sources in lower-case with hyphenated descriptors (e.g.
  `awesome-data-scientist.tex`) and co-locate assets they depend on.
- Retain the comment banners
  (`%-------------------------------------------------------------------------------`)
  to separate sections and aid quick scanning.
- Do not commit transient `.aux`, `.log`, or cache files; verify `.gitignore`
  covers any new artifacts you introduce.

## Fonts & Assets

- Rely on the fonts bundled via `awesome-cv.cls` (`Roboto`, `Source Sans Pro`)
  and avoid adding large binaries unless they are redistributable.
- Store new icons or imagery under `examples/` next to the document that uses
  them, and update `icon.png` only when the brand mark genuinely changes.
- Document FontAwesome or font configuration updates in the PR description so
  downstream users can adjust their toolchain.
