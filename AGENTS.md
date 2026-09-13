# Repository Guidelines

## Project Structure & Module Organization

This repository is a course workspace, not an application package. Keep subject material separated:

- `Mecanica_Ejercicios/` contains mechanics study material, such as the flexion guide.
- `Dibujo/` contains drawing-related coursework.
- `SolidWorks_Modelos/` contains CAD models; do not rename or move model dependencies casually.
- `tmp/pdfs/` contains rendered, disposable PNG previews of source workshop PDFs and the rendering helper.
- `Guia_estudio_circuitos.md`, `Guia_estudio_MAS.md`, and `Guia_estudio_ondas.md` are the maintained worked-study guides.

Keep original PDFs outside this workspace untouched. Add new study guides at the root using descriptive Spanish names, for example `Guia_estudio_estatica.md`.

## Build, Test, and Development Commands

There is no web application, package manifest, or automated build system. The available helper regenerates PDF previews:

```powershell
python tmp/pdfs/render_pdf_pages.py
```

It requires `pymupdf` and `Pillow` and reads the two PDF paths declared in `SOURCES`. Run it only when source PDFs or preview settings change. Review generated PNGs before relying on diagrams or numeric values.

## Coding Style & Naming Conventions

Use Markdown for study guides, with one H1 title, readable LaTeX, explicit SI units, and a short conceptual check after calculations. Preserve source problem numbers (for example, `15.50`). For Python, use four-space indentation, `snake_case`, `pathlib.Path`, and small direct scripts. Do not invent missing values from blurred diagrams; mark the ambiguity instead.

## Testing Guidelines

No automated test framework exists. For changes to `render_pdf_pages.py`, run the command above and verify that every expected page and contact sheet is created in `tmp/pdfs/`, with legible labels and no cropped circuit elements. For study-guide changes, cross-check equations, units, signs, and diagrams against the source PDF.

## Commit & Pull Request Guidelines

This directory is not currently a Git repository, so no local commit history defines conventions. If Git is initialized, use Conventional Commits, e.g. `docs: add waves study guide`. Keep commits scoped to one subject or helper change. Pull requests should state the source material, affected guide paths, validation performed, and screenshots only when rendered diagrams changed.

## Agent-Specific Instructions

Treat PDF diagrams as primary evidence. Do not create replacement applications unless explicitly requested after confirming the existing platform and its location.
