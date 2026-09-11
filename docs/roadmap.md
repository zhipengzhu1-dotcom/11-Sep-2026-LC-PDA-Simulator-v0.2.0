# Cycle maps and specification history

The public repository starts with v0.2.1. Earlier development took place in a separate
repository. The maps below summarize those completed cycles; the historical specs
are included locally so no private issue-tracker access is required. Legacy ticket
numbers in code and research belong to the original tracker.

| Cycle | Planning map | Scope | Specification |
|---|---|---|---|
| v0.1.0 | Original map #1, complete | Two scouting runs, LSS fit, linear-gradient prediction, widths, resolution, diagnostics, session save/load | [v0.1.0 snapshot](history/v0.1.0-spec.md) |
| v0.2.0 | Original map #41, complete | Independent candidate start/end, ramps and holds, composition diagnostics, programme overlay, session schema 2, geometry fallback for t0 | [v0.2.0 snapshot](history/v0.2.0-spec.md) |
| v0.2.1 | Public release preparation, complete | Post-v0.2.0 fixes and refactoring, public onboarding, example, CI, portable browser check | [Current SPEC](../SPEC.md), [release notes](releases/v0.2.1.md) |

## v0.1 cycle map

1. Define the LSS science model, input contract, and validation bar.
2. Implement the pure numerical engine, two-run fitting, widths, and resolution.
3. Build the Streamlit cockpit, diagnostics, and inputs-only session persistence.
4. Validate against reference calculations and held-out measured runs.

Original tag: September 1, 2026, source commit `1046311`.

## v0.2 cycle map

1. Rescope from the proposed optimizer to gradient freedom.
2. Establish composition extrapolation diagnostics and bench acceptance evidence.
3. Implement the programme walker, independent composition range, and schema 2.
4. Add paired programme tables, overlay, and calibrated composition-window readout.
5. Validate numerical integration, compatibility, diagnostics, and held-out runs.

Original tag: September 4, 2026, source commit `1f99d13`.
The optimizer plan was deferred; it is not a v0.2 feature. v0.2.1 incorporates the
later source snapshot `2591203` and the public-release preparation, without moving
either original tag or importing the private repository's Git history.

## Future cycles

These are planned scope, not delivery dates or implemented features.
Authority: [SPEC.md, §11](../SPEC.md).

| Cycle | Planned scope |
|---|---|
| v0.3 | CSV import, automatic peak matching, ≥2-run regression, isocratic mode |
| v0.4 | Temperature model |
| v0.5 | Colleague hosting and sharing |
| v0.6 | pH model |
| v0.7 | Resolution map and optimizer over live axes |
| v0.8 | Column selectivity database and method transfer |
| v0.9+ | Structure-based prediction |
