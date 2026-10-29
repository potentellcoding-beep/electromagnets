# Paperclip lifting model (lift-v1)

This is a deterministic classroom illustration, not an experimentally calibrated prediction. Model constants make a plausible small-nail scenario but do not establish accuracy for a particular real holder, battery, wire, nail or paperclip.

## Inputs and assumptions
- Nominal tapped source voltages: 1.5, 3.0, 4.5, 6.0 V. Four D cells remain in the holder; the fixed common and selected tap include one through four cells.
- 25 or 50 wraps, with unchanged core geometry and coil length.
- Lumped source/lead resistance: 2 Ω; extra wire: 0.02 Ω per wrap. These are assumed values, not measurements of the photographed holder.
- Effective magnetic gap: 0.0008 m; nail tip area: 20e-6 m².
- Contact/leakage efficiency multiplier: 0.65. Magnetic field limited to 1.2 T.
- Pool: 30 identical small steel clips, 0.0005 kg each. g=9.81 m/s².

## Calculation
R=2+0.02N. I=V/R when on, zero when off. μ₀=4π×10^-7. B=min(1.2,μ₀NI/gap). Usable force F=0.65B²A/(2μ₀). Clip capacity=min(30,floor(F/(clip mass×9.81))). Relative field metric is NI/15, based on 25 wraps at 1.5V.

The force expression is an ideal magnetic-gap approximation multiplied by an assumed efficiency. Real clip-to-nail interactions have complex geometry. The drawn bundle represents shared contact near a pole, not a long hanging chain. The model omits changing battery behavior, heating, detailed core magnetization and remanence. A power-off pickup therefore gives zero.

## Expected counts
| Voltage | 25 wraps | 50 wraps |
| --- | --- | --- |
| 1.5 V | 0 | 1 |
| 3.0 V | 2 | 6 |
| 4.5 V | 5 | 14 |
| 6.0 V | 9 | 26 |

Lifting is a threshold process: a nonzero field can be too weak to lift one clip. Doubling voltage at fixed wraps doubles current and field in this model, and quadruples ideal force; integer rounding and the pool limit affect clip counts. More wraps also increase resistance, so doubling wraps does not double current-times-turns at fixed voltage.

## Notebook
Every pickup records a snapshot and UTC timestamp. Configuration changes reset the visible pickup and do not alter old rows. Powered-off baselines remain in the log/CSV but are excluded from powered setup averages. Storage uses fieldwork-paperclips-v2, retains the newest 200 rows, and rejects rows inconsistent with this model. Older field-only notebook values cannot be reinterpreted as clip measurements and remain separate.

For physical calibration, collect actual clip mass, wire resistance, nail dimensions and repeated lifting data under a specified contact procedure, then revise the model and increment its version. Do not fit these constants silently or relabel the current counts as observed data.
