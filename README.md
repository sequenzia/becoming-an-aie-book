# Becoming an AI Engineer

## The Path from Software Engineer to AI Engineer

This directory contains the complete editorial blueprint for a practical textbook aimed at experienced software engineers who are new to machine learning. It specifies 30 chapters across eight parts, an estimated 500 pages of main text, a recurring support application, side labs, and evidence of learner competence.

The deliverable is a book blueprint. The manuscript, runnable companion application, datasets, and lab results are future authoring work; their specifications here do not represent completed implementations or experiments.

## Review the blueprint

- [Editable Word document](becoming-an-ai-engineer-blueprint.docx): the complete review copy.
- [Detailed outline](book-outline.md): chapter briefs, prerequisites, workshops, failure exercises, completion evidence, and reading references.
- [Research foundation](research/report-source.md): source-backed rationale, limitations, and editorial implications.
- [Project and assessment design](project-and-assessment.md): recurring application, milestones, capstone criteria, companion material, and authoring checks.
- [Source ledger](research/sources.json): source provenance, supported claims, qualifications, and chapter mappings.

## Maintain the blueprint

Edit `chapters.json`, `research/report-source.md`, `research/sources.json`, and `project-and-assessment.md`. Run `scripts/build_blueprint.py` using a Python environment with python-docx installed to regenerate the outline and Word document. In Codex, use the bundled Python runtime returned by the workspace dependency loader. The builder validates the chapter sequence, prerequisites, source references, and page allocations before writing outputs.

The Word file must be rendered and visually reviewed after changes. Markdown generation and structural checks alone do not establish layout quality. Review images and renderer logs belong in temporary storage, outside this directory.

Research was consulted on September 5, 2026. Source publication dates are preserved separately from access dates. Recheck changing model behavior, tooling, security guidance, and provider terms when drafting and before publication.
