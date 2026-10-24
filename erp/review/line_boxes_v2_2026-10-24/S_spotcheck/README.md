# S spot-check of verdicts_R.csv — 2026-10-24 10:50 Makkah
- fix1.jpg / fix2.jpg: all 30 `fix` boxes (green = R, red = text_locate v2 proposal). 15 located + 15 manual.
- ok0..ok2.jpg: 60 random `ok` proposals (seed 7).
- outliers.jpg: 17 `ok` boxes whose width/height per label digit is <0.33 or >0.62 (p5=0.36, p50=0.44, p95=0.61).
Findings: 30 fixes visually correct (digits-only, integer part), 0 wrong. 60 random ok: 0 clearly wrong. Outliers: boxes a bit loose/tight but the reader read the label from them (text_locate acceptance), so digit alignment holds.
Label/display digit-count mismatches to exclude from READER training (keep for locator): 93cbc282 (label 004652, display 04652), document-f60b (label 2790, display 002790). Owner to look at 345ef2a1 (331 vs 337) and pending-2744 (334/337) — readings are owner's domain.
