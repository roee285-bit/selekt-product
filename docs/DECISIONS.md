# סלקט — Decision Log

יומן זה נועד למנוע מצב שבו החלטות מוצר נשארות רק בשיחות.

## פורמט
### YYYY-MM-DD — כותרת
- **Decision:** מה הוחלט.
- **Why:** למה.
- **Impact:** מה צריך להשתנות במוצר / פיתוח / תוכן.
- **Source:** מסמך / שיחה / Issue.

---

### 2026-10-05 — הפרדת Product Management מ-Development Repository
- **Decision:** `selekt-product` ישמש לניהול מוצר, תוכנית עבודה, החלטות ו-Launch; קוד הפיתוח יישאר ב-repo נפרד.
- **Why:** סלקט כולל עבודה עסקית, ספקים, תוכן, משפטי ו-QA שאינה קוד.
- **Impact:** Issues מוצריים מנוהלים כאן; משימות קוד יקושרו בעתיד ל-repo הפיתוח.
- **Source:** החלטת עבודה משותפת.


### 2026-10-05 — MVP Scope Lock
- **Decision:** ננעל baseline מוצרי חדש באמצעות `docs/SCOPE_LOCK_2026-10-05.md`. המסמך הוא Delta מחייב לאפיון הראשי עד לאיחודו לגרסה חדשה.
- **Key changes:** גפ"ן כמקור אמת ברמת PROGRAM; Activity Format חד-פעמי/מתמשך/שניהם; התאמה לחינוך מיוחד ברמת PROGRAM; Multi-region לספק; קטגוריית "שפות והעשרה לימודית"; הפרדה מוחלטת בין profile approval ל-SELEKT Verified; סטטוס `rejected` לספק; naming אחיד ל-Lead/Review; Legal MVP additions.
- **Unchanged:** 20–100 Supply First, חיפה והצפון, guest discovery, filter-based MVP, Leads via WhatsApp/phone, reviews after `closed_won`, free launch.
- **Impact:** Backlog ו-QA חייבים לעבוד לפי ה-Scope Lock ולא לפי שמות/הנחות legacy.
- **Source:** האפיון הראשי + Implementation V2 + Legal Pack V2 + GEFEN review + החלטות מוצר מאוחרות.
