# m5b shards — 2026-10-24
m4 (903) + 172 pseudo-labelled (pseudo_label.py, dual-pair+TTA agreement) + 349 label-verified fast-located photos
(label_locate_fast.py: locator proposals, accepted only when the reader's string == human label exactly; meter box
synthesised around the line because these photos had no agent-D box) + 50 text_locate_m5_boxed.
VAL byte-identical to m4 val (177). 80 new photos dropped (pHash cluster of a val photo). Train 1048 / val 177.
Recombine: `cat m5b.tgz.part* > m5b.tgz && tar -xzf m5b.tgz -C <repo>/data/erp/ft/`.
