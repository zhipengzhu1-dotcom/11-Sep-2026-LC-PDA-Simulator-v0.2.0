# Documentation and repository map

Start with the [project README](../README.md) and [loadable example](../examples/README.md).

| Need | Read |
|---|---|
| Run the app | [Running guide](running-the-app.md) |
| Understand versions and planned scope | [Cycle maps and roadmap](roadmap.md) |
| Read the public release notes | [Release notes and review](releases/v0.2.1.md) |
| Contribute code or feedback | [Contribution guide](../CONTRIBUTING.md) |
| Find the authoritative requirements | [SPEC.md](../SPEC.md) |
| Understand names and architectural rules | [Domain vocabulary](../CONTEXT.md), [repo standards](../CLAUDE.md), [architecture decisions](adr/) |
| Check scientific assumptions | [Research](research/), [validation protocol](../validation/PROTOCOL.md) |
| Explore learning material | [Teaching mission](../teach/MISSION.md), [resources](../teach/RESOURCES.md) |
| Read historical specifications | [v0.1.0](history/v0.1.0-spec.md), [v0.2.0](history/v0.2.0-spec.md) |

## Codebase map

```text
streamlit_app.py       Streamlit entry point and screen composition
src/hplcsim/          Pure numerical engine, models, fitting, session schema
app/                  Input conversion, prediction pipeline, diagnostics, display
  screen_state.py     Sole owner of Streamlit session state
  entry.py            User input to domain models and engine units
  pipeline.py         Fit and predict orchestration
  session_io.py       Screen inputs to/from the session file
  wording.py          Diagnostic messages
examples/             Small, loadable public examples
validation/           Measured data, provenance, and preregistered predictions
tests/                Numerical, reference, measured-data, and app checks
scripts/              Browser verification tools
teach/                HTML learning material
docs/                 Roadmap, research, decisions, screenshots, historical specs
.github/              CI and feedback templates
```

Dependencies point from the app to the engine. The engine imports no UI libraries.
Keep the root entry point where it is: Streamlit's import behavior is covered by
`tests/test_entry_point.py`. Only the engine is packaged in the wheel; running the UI
requires the repository checkout and the `app` dependency extra.

Scientific evidence and screenshots retain their established paths. Versioned specs
under `docs/history/` preserve the earlier requirements. The original private issue
tracker and session handoffs are not required to build or use this public repository.
Legacy ticket numbers in code and research refer to that development history, not to
issues in this repository. Current bugs and feedback belong in this repository's issues.
Local agent tools, raw exports, personal workbooks, and caches are not release inputs.
