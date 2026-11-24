# Copilot instructions

## Context
- Repository goal: “rhetornet” is a debate/discussion analysis and visualization tool (see README); codebase is currently a skeleton.
- Primary artifact today: analysis.qmd (Quarto/markdown notebook, empty right now) intended to hold narrative, data wrangling, and visualizations.
- Python-oriented setup: .gitignore mirrors the canonical Python template; a local .venv folder exists (ignored) and should remain out of version control.
- License: MIT in LICENSE.

## Working conventions
- Keep analysis inside the Quarto notebook: prefer Python code chunks in analysis.qmd for data prep, modeling, and plots so the narrative stays close to the code.
- If adding Python modules, place them under a new src/ or notebooks-friendly helper module and import them from analysis.qmd to keep duplication low; avoid scattering ad-hoc scripts.
- Do not commit data, model artifacts, or notebook outputs; keep datasets small and documented paths relative to the repo root.
- When adding dependencies, record them in a requirements.txt and install into the existing .venv (activate via .venv/Scripts/Activate.ps1 on Windows).
- Favor reproducibility: seed randomness in analysis, and prefer deterministic library options when available.

## Running and verification
- Authoring loop: edit analysis.qmd, run code chunks in the Quarto environment (or via the Python kernel) to iterate quickly.
- Rendering: once content exists, build with `quarto render analysis.qmd` to produce HTML/PDF outputs; keep rendered artifacts out of git.
- If you add tests or helper modules, wire them to pytest and run `pytest` inside the activated .venv; add minimal fixtures rather than large fixtures checked into git.

## Documentation and hygiene
- Update README with any new workflows (environment setup, data acquisition steps, render commands) as they emerge.
- Respect the existing Python .gitignore; do not add IDE/OS cruft or environment caches.
- Prefer clear, commented code chunks in analysis.qmd only when logic is non-obvious; keep the notebook narrative concise and task-focused.

## When in doubt
- Ask for the expected data inputs and visualization targets before adding structure, since the analysis.qmd is currently empty and requirements are not yet captured.
- Keep changes minimal and documented so future agents can pick up quickly.
