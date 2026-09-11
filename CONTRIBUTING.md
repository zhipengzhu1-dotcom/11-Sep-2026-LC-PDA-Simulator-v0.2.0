# Contributing

Bug reports, usability feedback, and comparisons with measured chromatography are
welcome. Use the [issue templates](https://github.com/zhipengzhu1-dotcom/11-Sep-2026-LC-PDA-Simulator-v0.2.0/issues/new/choose).
Give the version or commit, steps, expected behavior, and actual result. For a
prediction mismatch, include method units, scouting inputs, measured confirmation
results, and warnings shown. Share only data you can make public.

## Development setup

Install [uv](https://docs.astral.sh/uv/), clone the repository, and run from its root:

```bash
uv sync --locked --python 3.12 --extra app
uv run --locked --extra app streamlit run streamlit_app.py
```

The app extra is required for the full tests as well as the UI. The wheel contains
only `src/hplcsim`; contributors work from a checkout. Python 3.12 is the validation
baseline; package metadata allows newer Python versions but they are not all tested.

## Before submitting a change

```bash
uv run --locked --extra app pytest
uv run --locked --extra app ruff check
uv run --locked --extra app ruff format --check
uv run --locked --extra app mypy
```

CI runs these gates on Python 3.12 and verifies pinned rows in Chromium. For changes to pinned-row CSS or placement, also
run the real-browser gate in [the running guide](docs/running-the-app.md). Pytest
cannot verify scrolling or browser-held widget state.

Read [CLAUDE.md](CLAUDE.md) for architecture and unit conventions and
[SPEC.md](SPEC.md) for requirements. Scientific changes must preserve the numerical,
reference, and measured-data acceptance layers; document evidence in `docs/research/`.
Keep UI imports out of the engine, and session-state access in `app/screen_state.py`.

Use a focused branch and PR, describing the problem, resulting behavior, and checks
run. Add meaningful regression coverage for behavior changes. Discuss changes to
scientific assumptions or planned scope in an issue first. No AI tooling or private
artifact access is needed to contribute.

## File organization

Follow the [repository map](docs/README.md). Put runnable example sessions in
`examples/`, scientific evidence in `docs/research/` and `validation/`, and dated
historical records in `docs/handoffs/`. Preserve measured data and its provenance.
Do not commit local agent tools, caches, raw instrument exports, or personal workbooks.
