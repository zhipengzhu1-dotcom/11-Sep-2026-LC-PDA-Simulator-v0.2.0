# LinkedIn announcement draft

I've released LC-PDA Simulator v0.2.1, an open-source HPLC gradient simulator for
chromatographers, and I'm looking for public feedback.

Start with two scouting runs, fit an LSS retention model, and explore candidate
gradients with different start/end compositions, ramps, and holds. The app displays
predicted retention times, widths, resolution, and chromatograms, with diagnostics
when a candidate departs from the calibration conditions.

The repository includes a loadable lab example, validation evidence, and instructions
for running it locally. Multi-segment resolution is not validated; the release notes
explain the model's limitations. This version models chromatography, not PDA spectra.

I'd especially value feedback on setup, the gradient-table workflow, and comparisons
with measured runs. What would make this useful in your method-development workflow?

Release: https://github.com/zhipengzhu1-dotcom/11-Sep-2026-LC-PDA-Simulator-v0.2.0/releases/tag/v0.2.1

Feedback: https://github.com/zhipengzhu1-dotcom/11-Sep-2026-LC-PDA-Simulator-v0.2.0/issues/new/choose
