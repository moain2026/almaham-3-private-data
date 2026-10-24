# verdicts_R summary (Agent R, 2026-10-24)

Total rows: 462 (379 proposals + 83 unlocated), unique filenames, none missing.

## Count per verdict

| verdict | proposals | unlocated | total |
|---|---|---|---|
| ok | 351 | 0 | 351 |
| fix | 15 | 15 | 30 |
| reject | 13 | 68 | 81 |

Of the rejects, 43 are "mechanical".

## Count per meter type

| meter_type | ok | fix | reject |
|---|---|---|---|
| CHINT | 0 | 0 | 3 |
| CRYSTAL | 55 | 7 | 12 |
| GLORY | 3 | 1 | 0 |
| KENWELL | 5 | 0 | 0 |
| MECHANICAL | 0 | 0 | 34 |
| OTHER | 24 | 4 | 9 |
| SMART_YELLOW | 75 | 8 | 13 |
| TAGADOD | 19 | 0 | 5 |
| TOMAS_SMART | 166 | 6 | 4 |
| TOMAS_STATIC | 4 | 4 | 1 |

## Reading vs display (for owner, readings NOT changed)

- 345ef2a1-3389-448c-a3df-4e1268ff2f67.jpg: reading mismatch: display shows 331 (label 337)
- document-f60bd56f-f813-5ef5-9852-56b92c99137f.jpg: label 2790 omits leading zeros shown on display (002790)
- pending-274446ed-5f18-4932-b0e5-a8a6e9c1734f-ad5acb2d1dc206ffb9769f1f28af81270be005a61a720466b0b51451f119505f.jpg: unreadable: top half washed out, last integer digit uncertain (334 vs 337)

## Coordinates

All boxes (x1,y1,x2,y2) are in original-photo pixels **after EXIF orientation is applied** (PIL `ImageOps.exif_transpose`), the same frame as `line_box_photo_px` in proposals.json.

## Open item — unlocated photos R did not box

19 unlocated photos show an electronic display that looks readable, but R ran out of review time before boxing them. They are marked `reject` with the note "not boxed by R ..." so they are NOT approved. They need a manual box from another reviewer:

- ab3a71bf-a5b0-48d5-8289-f90a93d6ca74.jpg
- b1da0c15-349b-4301-8689-b5f9d16f3411.jpg
- bcda6584-800c-4225-a23e-c252bbbc4498.jpg
- bf12d416-482c-49ef-8b01-58feae2b3a8d.jpg
- cce29167-520f-4931-8201-426b14e9139e.jpg
- daf477b1-9c79-4c71-9a99-ea2d9deb4331.jpg
- dca19770-1dfd-46d4-9f72-7c0093f3b786.jpg
- dcf8aa32-fcc8-4ec2-bc6c-ba8ddfdee42b.jpg
- document-013828a1-8d07-5ce5-9f1e-1cd50a9f5778.jpg
- document-0c8b091f-2597-5038-92d2-937d605c5ec4.jpg
- document-88fce49b-99ed-58ec-9095-f79e1c412e6b.jpg
- document-98d6611b-1342-5e60-81db-7888b53390a7.jpg
- document-993af03f-d435-408f-90ba-4749ca3f5ba2.jpg
- document-ec84e70b-199a-552c-84ed-a966e99b97fe.jpg
- f1d64e33-84e9-489c-8f5e-b944668a3bb9.jpg
- pending-0c587e3d-2a1c-59c3-a338-4afebc7534c3-c4d855626cf83d0d5d2cd357b18bcd89e0ead145b2f041417b8ab520f9136f41.jpg
- pending-310286cc-7b79-524f-8199-aaf52372998c-4b1176ac0bdfd7c5961e9ddc6f09fd3891c80d46cef24bd8309ccfb27671c57e.jpg
- pending-59a94e42-fcfb-4f18-adff-6f8ef98e5dcf-b01544a77593fd48a91ffdbd5ec539491adf973abbca91a084b20dd6904fe240.jpg
- pending-c74dac5f-c3ce-5f5e-95ff-af81f7757a14-54cfc633c71c3109f16530b312d14ff5322ef59e05987b725ae93c368b0502ca.jpg
