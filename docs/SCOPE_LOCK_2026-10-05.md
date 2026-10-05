# סלקט — Scope Lock ל-MVP
**תאריך:** 2026-10-05  
**סטטוס:** LOCKED — baseline מוצרי לניהול ה-Backlog.

מסמך זה הוא Delta לאפיון הראשי. הוא אינו מחליף את האפיון הראשי; במקום שבו קיימת סתירה, ההחלטה המפורשת במסמך זה גוברת עד שהאפיון הראשי יעודכן בגרסה מאוחדת.

## מקורות שנבדקו
- מסמך האפיון הראשי: SELEKT — מסמך אפיון MVP.
- מסמך היישום: "סלקט – איפיון לקלוד V2 – מוצר × משפטי × יישום".
- Legal Pack V2.
- SELEKT_Gefen_Market_Review.
- תוכנית הבדיקות MVP1.
- החלטות מוצר שאושרו לאחר גרסת האפיון המקורית.

---

## 1. CURRENT — נשאר ללא שינוי

ההחלטות הבאות נשארות מחייבות:
- ההשקה ממוקדת חיפה והצפון.
- השימוש חינמי בשלב ההשקה.
- Supply First נשאר יעד מוצרי של 20–100 ספקים איכותיים לפני יצירת ביקוש אקטיבי. ניסויי Wedge / Concierge / Density אינם מחליפים החלטה זו אלא משמשים ללמידה.
- ACCOUNT הוא ישות זהות אחת ויכול להחזיק כמה פרופילי תפקיד.
- SUPPLIER_PROFILE ו-PROGRAM הן ישויות נפרדות; לספק אחד מספר תוכניות.
- חיפוש וצפייה כאורח ללא login wall.
- חיפוש MVP מבוסס Filters + Inspiration Chips קבועים; אין LLM/free-text search.
- שני CTA ליצירת קשר: WhatsApp ו-"הצג פרטי קשר"; שניהם יוצרים LEAD.
- ספק רואה לידים שהגיעו אליו בלבד ואינו משנה סטטוס ליד ב-MVP.
- FAVORITE למשתמש רשום.
- REVIEW רק עבור משתמש רשום, על Lead שלו שהגיע ל-closed_won, לכל היותר ביקורת אחת לליד, ובאישור אדמין לפני פרסום.
- אין תשלום, עמלה, סליקה, RFP, Event Workspace או AI Search ב-MVP.

---

## 2. REPLACE — גפ"ן: Program הוא מקור האמת

### החלטה
סטטוס גפ"ן הוא מאפיין של PROGRAM, לא של SUPPLIER.

### התנהגות
- כל תוכנית מציגה את הסטטוס שלה.
- ספק יכול להחזיק תוכניות עם סטטוסי גפ"ן שונים.
- סיכום ברמת Supplier, אם מוצג, הוא Derived בלבד ומחייב tooltip שמפנה לבדוק את התוכנית הספציפית.
- פילטר גפ"ן ב-Discovery נבחן מול התוכנית הספציפית, לא מול תג כללי של הספק.

### שפה ציבורית
ב-UI הציבורי משתמשים בשפה המקובלת: **מסלול ירוק / מסלול כחול**.  
לא מציגים למשתמש את ניסוחי ה-enum הטכניים `tender / non_tender` ולא משתמשים ב"מכרזי / לא מכרזי" ככותרת התג.

### Data
ה-enum הטכני הקיים יכול להישאר זמנית לצורך תאימות, כל עוד המיפוי ל-UI חד-משמעי:
- `tender` → מסלול ירוק
- `non_tender` → מסלול כחול
- `none` → ללא תג גפ"ן

אין להוסיף "מסלול סגול" ל-MVP כסיווג תוכנית ספק ללא החלטה נפרדת.

---

## 3. REPLACE — PROGRAM: חד-פעמי / מתמשך / שניהם

### החלטה
לכל PROGRAM יש מאפיין אופן פעילות נפרד מ-`event_type`.

ערכים עסקיים:
- חד-פעמי
- מתמשך / קבוע
- שניהם

### כלל
תוכנית אחת רשאית להציע את אותו תוכן גם כסדנה חד-פעמית וגם כחוג/תהליך מתמשך; לכן אסור למודל לכפות בחירה בלעדית בין השניים.

### MVP
המאפיין חייב:
- להישמר ברמת PROGRAM.
- להיות ניתן לעריכה ע"י הספק/אדמין בהתאם להרשאות.
- להיות מוצג בעמוד התוכנית.

הפיכתו לפילטר Discovery היא הרחבה נפרדת ואינה תנאי ל-Scope Lock זה.

---

## 4. REPLACE — התאמה לחינוך מיוחד ברמת PROGRAM

### החלטה
נוסף מאפיין תוכנית: התאמה לחינוך מיוחד.

### כללים
- המאפיין שייך ל-PROGRAM, לא לספק.
- זהו נתון שמוסר הספק; הוא **אינו** חלק מ-SELEKT Verified ואינו מעיד שסלקט בדקה התאמה מקצועית/רגולטורית.
- ערכי MVP: `not_specified / suitable / not_suitable`.
- תג ציבורי "מתאים לחינוך מיוחד" מוצג רק כאשר הערך `suitable`.
- אין להציג תג שלילי כאשר `not_suitable`; פשוט לא מציגים את תג ההתאמה.
- tooltip/קופי צריך להבהיר שמדובר במידע שנמסר ע"י הספק.

פילטר ייעודי יכול להתווסף לאחר בדיקת UX; הוא אינו תנאי לשדה ולתג ב-MVP.

---

## 5. REPLACE — אזורי שירות: Supplier יכול לשרת מספר אזורים

### פער
הסכמה המקורית מחזיקה `region_id` יחיד ב-SUPPLIER_PROFILE.

### החלטה
ספק יכול לשרת מספר אזורים.

### MVP
- מקור האמת הוא Multi-select של אזורי שירות ברמת SUPPLIER.
- חיפוש לפי אזור מחזיר ספק כאשר אזור החיפוש נמצא באחד מאזורי השירות שלו.
- PROGRAM יורש את אזורי השירות של הספק ב-MVP.
- אם יידרשו בעתיד אזורים שונים לכל תוכנית, זו הרחבה נפרדת.

### Data
אין להשאיר את `region_id` היחיד כמקור אמת. יש להשתמש ב-relation / join table או מימוש רב-ערכי מקביל שמאפשר FK תקין.

---

## 6. REPLACE — Category LOV

קטגוריית MVP מאושרת להוספה:
- **שפות והעשרה לימודית**

יש לבצע migration/cleanup כך שלא ייווצרו שתי קטגוריות ציבוריות חופפות רק בגלל ערך ישן כגון "שפות ותקשורת". החלטת המיפוי של רשומות קיימות צריכה להיות מפורשת ומתועדת.

---

## 7. REPLACE — Supplier publication ≠ SELEKT Verified

### Profile publication
`profile_status=approved` פירושו שהפרופיל הושלם ואושר להצגה בלבד.

### SELEKT Verified
התג ניתן כאשר:
1. פרופיל הספק מלא לפי רשימת שדות חובה מאושרת.
2. שתי המלצות נפרדות מגנים/מוסדות אומתו.
3. אדמין מאשר `verification_status=verified` על בסיס התנאים לעיל.

### אסור לטעון שהתג כולל
- בדיקת עבר פלילי.
- בדיקת ביטוח.
- בדיקת רישיונות.
- בדיקת בטיחות.
- בדיקת כל מדריך/עובד.
- ערבות לאיכות או לביצוע עתידי.

### Recommendation flow
ה-flow שאושר ל-MVP:
- קישור המלצה תקף 14 יום.
- הקישור מיועד להגשה אחת.
- סטטוסים תפעוליים: `sent / answered / verified`.
- רק המלצה שאומתה נחשבת לשתי ההמלצות הנדרשות ל-Verified.
- רק תוכן המלצה שאושר להצגה יוצג ציבורית, בהתאם לכללי הפרטיות/משפטי.

---

## 8. REPLACE — Supplier rejection

ה-Admin יכול לאשר או לדחות ספק ולכן `profile_status` חייב לתמוך גם ב-`rejected`.

Baseline:
- `incomplete`
- `pending_review`
- `approved`
- `rejected`

כלל:
- רק `approved` ציבורי.
- ספק שנדחה יכול לערוך ולהגיש מחדש; הגשה מחדש מחזירה ל-`pending_review`.
- `rejected` אינו זהה ל-`blocked` ברמת ACCOUNT.

---

## 9. REPLACE — שמות סטטוסים אחידים

ה-naming המחייב ל-MVP:

### LEAD
`contact_initiated → not_contacted / pending → closed_won / closed_lost`

שמות ישנים כגון:
- `initiated_contact`
- `contacted_not`
- `won_closed`

נחשבים Legacy ואסור להשתמש בהם בקוד חדש, בדיקות או מסמכים.

### REVIEW
`pending_review / approved / rejected`

`review_pending` הוא Legacy.

---

## 10. ADD — שכבת Legal מינימלית היא MVP1/P0

היישום המשפטי שאושר אינו V2 עסקי; הוא תנאי השקה ל-flows הקיימים.

### נדרש
- `LEGAL_ACCEPTANCE` עם לפחות: account_id, document_key, version_id, accepted_at, acceptance_context.
- מקור מרכזי ל-legal copy/versions.
- checkbox חובה מתאים בהרשמת מזמין וספק; marketing נפרד ואופציונלי.
- Terms / Privacy / Supplier Terms / Reviews Policy / Verified Policy והעמודים הנדרשים לפי Legal Release.
- Disclosure מתאים ליד WhatsApp ול-Phone Reveal.
- Privacy/account closure request בסיסי.
- Report flow בסיסי עבור Supplier / Program / Review.
- audit מינימלי לפעולות Admin רגישות.

אין צורך ב-Legal CMS מלא ב-MVP.

---

## 11. V2 — נשאר מחוץ ל-MVP

בנוסף לפריטי V2 שכבר באפיון, נשארים בחוץ:
- ניהול זמינות מתקדם של תוכנית.
- impressions / search appearances / card clicks כ-analytics לספק.
- Lead status history.
- supplier analytics מתקדם.
- עדכון Lead status ע"י ספק.
- personalization.
- dynamic inspiration chips.
- payments/freemium.
- LLM search.

---

## 12. החלטות תפעול/יישום שלא משנות Scope — הועברו ל-Issues נפרדים

הנושאים הבאים אינם סיבה לפתוח מחדש את ה-MVP, אך חייבים החלטה לפני QA/Production:
- מניעת Lead duplicates וטיפול בכשל בין שמירת Lead לפתיחת WhatsApp/טלפון.
- transition matrix מלאה ללידים: direct close, reopen, חזרה ל-pending.
- רשימת שדות מדויקת ל-100% profile completeness.
- התנהגות Verified לאחר עריכת פרופיל/המלצה.
- חיבור Lead אורח לחשבון שנפתח לאחר מכן.
- אוכלוסיית חישוב דירוגים.
- deactivate/delete של LOV/Program כשיש היסטוריה.
- migration של category קיימת ל"שפות והעשרה לימודית".

---

## 13. Definition of Done ל-Scope Lock

- [x] נבדק האפיון הראשי מול מסמכי יישום/משפטי והחלטות מאוחרות.
- [x] פערי Program metadata הוכרעו.
- [x] גפ"ן ננעל ברמת PROGRAM.
- [x] Verified הופרד מאישור פרסום.
- [x] Lead/Review naming ננעל.
- [x] Multi-region ננעל.
- [x] Legal MVP הוגדר כתנאי השקה.
- [x] פריטי V2 נשמרו מחוץ ל-MVP.
- [x] נושאי implementation פתוחים הועברו ל-Issues ייעודיים.
