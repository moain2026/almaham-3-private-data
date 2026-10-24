# synthetic line shards dr1 + dr2 — 2026-10-24
line_dr1 (4000): `SYNTH_DR=1 SYNTH_LINE=int` dark/low-contrast panels, faint dot. Gave reader clean65 49->53.
line_dr2 (4000): `SYNTH_DR=2 SYNTH_LINE=int` + inverted polarity (35%), more glare/low light.
Regenerable from lab/synth2.py + gen_det_data.py (seed bases 6000/7000). Recombine: `cat synth_dr.tgz.part* > synth_dr.tgz`.
