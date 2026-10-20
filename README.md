# almaham-3-private-data — البيانات الخاصة لمشروع almaham-3

> **مستودع خاص (private).** يحوي صور عدادات عملاء وبيانات ثقيلة لا يجوز أن تدخل المستودع العام
> [`moain2026/almaham-3`](https://github.com/moain2026/almaham-3) (ADR-0004). **لا تجعله عاماً أبداً. لا تنسخ منه إلى العام.**
> القرار الرسمي: `almaham-3/docs/adr/0006-private-data-repo.md`. السكربتات: `almaham-3/scripts/private_data.sh`.

## لماذا هذا المستودع؟
المالك رفع صوراً إلى `almaham-3` فرفضها `.gitignore` بصمت (`**/photos/`, `/data/`) — لم تُحفظ. وكلّ ما نُزِّل في السندبوكسات القديمة (3,014 صورة ERP، 11 GB بيانات اصطناعية) **ضاع مع إغلاقها**. من الآن: كل ملف خاص أو ثقيل يُرفع هنا، مرة واحدة، ويُسحب في أي بيئة جديدة بأمر واحد.

## الهيكل
| المسار | ما فيه | الحجم المتوقع | التحقق |
|---|---|---|---|
| `photos_49/` | صور الاختبار الـ49 (`23065.jpg`…`23113.jpg`) — **للتقييم فقط، لا تدريب** | ~34 MB | `almaham-3/benchmark/data/photos.sha256` ⇒ 49/49 |
| `erp/photos/` | صور ERP المسمّاة (أسماء UUID) — للتدريب/التحقق | 2–3 GB (تُرفع على دفعات) | `erp/manifests/erp_photos.sha256` |
| `erp/manifests/` | `all_meter_photos.json` (فهرس الخادم)، قوائم الشرائح، بصمات | صغير | — |
| `weights_archive/` | نقاط حفظ وسيطة لا تدخل العام (العام فيه النهائية فقط) | ~1 MB لكل ملف | sha256 في `MANIFEST.md` |
| `logs_archive/` | سجلات تدريب كاملة (`/proc/<pid>/fd/1` عند الحاجة) | صغير | — |
| `results_archive/` | `data/review/e2e_*` (صور مراجعة تحوي قصوص عدادات) | متوسط | — |
| `phone/` | قياسات جوال المالك: `captures_log.csv`, `bench_*`, `rectcheck/` (قبل نسخ الملخص إلى العام) | متوسط | — |
| `synth_samples/` | عيّنات صغيرة من البيانات الاصطناعية (الكاملة 11 GB تُولَّد بالسكربت لا تُرفع) | صغير | — |

## القواعد
1. **حدود GitHub:** ملف ≤ 100 MB، push ≤ 2 GB. الصور تُرفع كما هي (jpg) على دفعات بـ `private_data.sh push-erp` (يقسّم تلقائياً).
2. **كل رفع يُسجَّل** في `MANIFEST.md` (التاريخ، ما أُضيف، العدد، sha256 للأرشيفات) وفي `almaham-3/STATUS.md`.
3. **لا أسرار** هنا أيضاً (لا كلمات مرور ERP، لا توكن). الفحص: `git grep -iE "passw|token|ghp_"` قبل كل push.
4. البيانات الاصطناعية الكاملة لا تُرفع (11 GB، تُعاد بـ `gen_det_data.py` ببذور ثابتة).

## الاستعمال من بيئة جديدة
```bash
# من داخل almaham-3 (يحتاج توكن له صلاحية repo في ~/.git-credentials)
bash scripts/private_data.sh pull           # يسحب هذا المستودع إلى ../almaham-3-private-data ويربط data/photos و data/erp/photos
bash scripts/verify_photos.sh               # ⇒ OK: 49/49 photos match
```
