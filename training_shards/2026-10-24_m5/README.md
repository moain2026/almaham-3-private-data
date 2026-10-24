# m5 shards — 2026-10-24
m4 (903 photos, pHash split) + 172 pseudo-labelled photos (lab/pseudo_label.py: candidate pair + reference pair + 4 TTA views all agree, strict gate) in TRAIN only.
VAL is byte-identical to m4 val (177; FIXED_VAL=m4_keys.json) so clean65 / val-m4 numbers stay comparable. 26 new photos dropped (pHash cluster of a val photo).
Train 884 / val 177. Weight of pseudo samples 0.5 (PSEUDO_W). Extract: `tar -xzf m5_shards.tgz -C <repo>/data/erp/ft/`.
Recombine: `cat m5_shards.tgz.part* > m5_shards.tgz` (GitHub 100MB limit).
