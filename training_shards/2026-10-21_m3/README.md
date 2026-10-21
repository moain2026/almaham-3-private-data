# Training shards snapshot — 2026-10-21 (agent S)
Resume training in a fresh sandbox WITHOUT recomputing text_locate (hours):
  cp *.npy *.json  <repo>/data/erp/ft/
  # reader shards: ft6_{train,val} (user-rect crops, 393/105) + m3_{train,val} (whole-meter, 463/68, _W = owner x2)
  # concat -> ft6m3 (see docs/runbooks/resume-training.md)   locator shards: m3_loc_{train,val}
  # text_locate_all.json: 1409 photos, line boxes from lab/text_locate.py (reader_ft6m1_augv2)
Synthetic shards (line_s1 893MB, scene_s1) are NOT here: regenerate with lab/gen_det_data.py (line 24000 ../data/synth/line_s1 1) or copy from Contabo /opt/almaham/almaham-3/data/synth/.
