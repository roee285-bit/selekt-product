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

### 2026-11-09 — חינוך מיוחד נדחה מ־MVP1
- **Decision (owner):** מאפיין ותווית ״מתאים לחינוך מיוחד״ ברמת PROGRAM אינם נדרשים בהשקה הראשונית; עוברים ל־V2 / post-launch, אלא אם תינתן החלטה חדשה.
- **Why:** תעדוף המוצר של בעל הפרויקט ב־2026-11-09.
- **Impact:** סעיף 4 ב־Scope Lock מ־2026-10-05 נשמר כהיסטוריה אך אינו Launch Gate מחייב; להסיר דרישה זו מקריטריוני Done של #3/#4/#8/#11 ולהוסיף ל־#12.
- **Source:** החלטת בעל המוצר בשיחת SELEKT מ־2026-11-09.

### 2026-11-09 — בירור פעילות מתמשכת ומקור ראיות הפיתוח
- **Decision:** אין לקבוע שחסר מימוש לפעילות מתמשכת: במסך DEV שהוצג מופיעים checkbox של פעילות מתמשכת, תדירות, משך מפגש ומינימום/מקסימום משתתפים; אותו מבנה מופיע ב־ZIP ב-`program-form.tsx` וב-`supplier/actions.ts`.
- **Remaining check:** הטופס שומר `is_ongoing` boolean ולא enum תלת־ערכי. יש לברר האם דרישת ״שניהם״ נענית באמצעות הזרימה הקיימת או דורשת שינוי, אך אין לתייג את **עצם הפעילות המתמשכת** כחסרה. לא בוצעה בדיקת DEV/PROD חיה.
- **Impact:** לתקן Audit/Board/Workplan, להבחין בין `code-present`, screenshot supplied by owner ו־`runtime-verified`.
- **Source:** צילום מסך בעל המוצר ו־`selekt-main.zip` בשיחה מ־2026-11-09.
