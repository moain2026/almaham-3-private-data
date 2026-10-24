# Training shards snapshot — 2026-10-24 m4 (agent S)
903 photos (m3 531 + 381 boxes verified by agent R, 9 poisoned excluded), pHash-cluster split 726 train / 177 val.
Built by: lab/build_m4_input.py -> text_locate_m4.json ; SPLIT=phash lab/build_meter_shards.py text_locate_all.json,text_locate_m4.json ../data/erp/ft/m4
Restore:
  cp *.npy *.json <repo>/data/erp/ft/ && cd <repo>/data/erp/ft && python3 -c "import numpy as np;np.save('m4_loc_train_X.npy',np.concatenate([np.load('m4_loc_train_X.part0.npy'),np.load('m4_loc_train_X.part1.npy')]))"
(m4_loc_train_X.npy was split into two parts for GitHub's 100 MB limit.)
meter_shards_m4.jpg = 60-sample audit sheet (red = line box used for training).
