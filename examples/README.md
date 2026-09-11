# Three-peak lab example

1. [Start the app](../docs/running-the-app.md).
2. Find **Session** in the left sidebar and upload `three-peak-session.json`.
3. The app fits the two scouting runs and predicts a 25-minute, 5 → 95 %B ramp
   after a 0.5-minute initial hold. The chromatogram and result tables should populate.

| Peak | Predicted tR (min, approximately) | Measured run 3 tR (min) |
|---|---:|---:|
| Unknown-1 | 13.871 | 13.787 |
| Unknown-2 | 16.740 | 16.658 |
| Unknown-3 | 24.395 | 24.358 |

The inputs come from [method.csv](../validation/method.csv),
[run1.csv](../validation/run1.csv), and [run2.csv](../validation/run2.csv).
Run 3 is held out of the fit. Measured scouting widths determine per-peak plate counts;
areas come from the source files. No predicted result is stored in the session JSON.
The session is schema 2 and uses t0 = 0.525 min, dwell = 0.9375 min, flow = 0.4 mL/min,
and a 100 × 2.1 mm, 1.6 µm core–shell column at 45 °C. The recorded
solvent-front provenance is included; the app correctly warns that this is not an
injected unretained marker.

Change the candidate's duration to 60 minutes and compare with
[run4.csv](../validation/run4.csv). Change its start or add a segment to explore
v0.2's gradient freedom and read the diagnostics alongside the prediction. These
changes are extrapolations of the same fitted model, not new measurements.

The dwell value comes from the instrument specification rather than a measurement;
t0 was read from the solvent front. Temperature is metadata. This widely separated
sample is useful for onboarding but does not establish near-critical resolution
accuracy. See [the protocol](../validation/PROTOCOL.md) and the separate
[four-peak validation sample](../validation/Validation_2/README.md).
