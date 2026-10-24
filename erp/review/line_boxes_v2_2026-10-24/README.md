# Line-box proposals for human/agent review — 2026-10-24 (agent S)
379 photos: human-verified READING exists (labels_agentD.csv) but the integer-line BOX was proposed automatically (text_locate v2).
Each `img/<filename>` = whole-meter crop (agent D's meter box) with the RED proposal box drawn. The reading + type is printed top-left.
`proposals.csv/json` = box in ORIGINAL photo pixels (x1,y1,x2,y2). `unlocated_need_manual_box.csv` = 83 photos with no proposal (box must be drawn by hand on erp/photos/<filename> inside meter_box_frac).
Task: for each row decide `ok` (box tightly covers ALL and ONLY the integer digits of the consumption line), `fix` (give corrected x1,y1,x2,y2), or `reject` (not readable / wrong line / wrong photo). Output format: see almaham-3 docs/handoff/prompt-for-reviewer-2026-10-24.md
