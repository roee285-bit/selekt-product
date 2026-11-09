# סלקט — תוכנית עבודה MVP → Launch

> מסמך Delivery מרכזי. תמונת העבודה היומית נמצאת ב-[Launch Board](BOARD.md). ה-Scope המחייב נמצא ב-[MVP Scope Lock](SCOPE_LOCK_2026-10-05.md).

## בדיקת DEV — עדכון ראיות (2026-11-09)

[דוח תצפית על עמוד הבית של DEV](DEV_HOME_READONLY_2026-11-09.md) — עמוד הבית נצפה בפועל דרך לשונית דפדפן **מחוברת למשתמש**: Hero, שדה חיפוש, קטגוריות, כרטיסי תוכניות, ספקים מסומני Verified וקישורי Legal. אלה **נוכחות ותוכן**, לא PASS של חיפוש, Leads, הרשאות או מסמכים משפטיים. בדיקות אורח, מעבר עמודים, לחיצות, 390/768/1280 ו־Production לא בוצעו בגלל מגבלת ניווט/רשת; אין לייחס חסם סביבתי לכשל ביישום.

- **#3 — Discovery:** Home content visible on DEV. לשמר את סטטוס ה־Issue פתוח עד בדיקת מסננים, תוצאות, התאמות ו־guest flow.
- **#4 — Program ongoing:** צילום המסך שהעלה בעל המוצר + הקוד מראים ממשק שדות לפעילות מתמשכת; לא לדרוש תיקון לפונקציונליות עצמה ללא ראיה.
- **#9 — Supply:** ב־DEV קיימים גם שמות ספקים/תוכניות של QA; אין להסיק מכמות הכרטיסים כי הושג יעד ספקים אמיתיים ב־Production.
- **#11/#17:** נדרש דפדפן אינטראקטיבי ברשת עם viewport מדויק וסשן אורח מבודד להמשך QA; אין שינוי סטטוסים.

---

## תיקון תוכנית — 2026-11-09 | בעקבות צילום DEV והחלטת מוצר

- **חינוך מיוחד:** נדחה על ידי בעל המוצר לשלב שאחרי MVP1, מועבר ל־V2 (#12); לא P0 ולא חסם Launch. סעיפי תוכנית העבודה הישנים שמציגים אותו כחסר ב־MVP הוחלפו בהחלטה זו.
- **פעילות מתמשכת:** קיימת בממשק המתועד ובקוד `is_ongoing` + תדירות + משך מפגש + משתתפים; **לא** לרשום את הפעילות המתמשכת כחסרה. מצב `שניהם` התלת־ערכי עדיין טעון בירור Acceptance בלבד, לא כישלון מאומת.
- **סביבת בדיקה:** נבדק ZIP בלבד, בתוספת צילום מסך DEV של בעל המוצר; **לא נבדקו DEV/PROD חיות**, build או DB. להימנע מהסבת ממצא סטטי לתקלה ב־Runtime.
- **NOW מתוקן:** 1) החלטות מוצר על Guest Leads, Multi-role, GEFEN וחריגות V2; 2) Legal versioning ובדיקת התאמת פעילות ״שניהם״ אם עדיין מחייבת; 3) QA/Runtime Evidence. חינוך מיוחד **לא** חלק משערי MVP1.

[יומן החלטות](DECISIONS.md) · [דוח ביקורת מתוקן](DEV_SNAPSHOT_AUDIT_2026-11-09.md)

---

## Current Plan — 2026-11-09 | ביקורת קוד השותף

**מקור עדכון:** `selekt-main.zip` שהועלה ב־9.11.2026, עם מצב פיתוח מתועד עד 25.10.2026. [דוח ביקורת סטטית וראיות](DEV_SNAPSHOT_AUDIT_2026-11-09.md). **לא** נבדקו live DB, Production, build, test execution או SHA של מקור הארכיון. הסטטוס להלן הוא **evidence-from-code**, לא Sign-off.
ה־[Scope Lock](SCOPE_LOCK_2026-10-05.md) נשאר בתוקף. חריגה בקוד אינה החלטת מוצר מאושרת.

### NOW — שלושה שערי עבודה
1. **שער החלטות מוצר (P0):** להכריע עם השותף האם שומרים על Guest Lead ללא הרשמה (#6), על Multi-role account (#5/#8), האם ומתי מציגים GEFEN (#3/#4), ומה עושים עם עדכון סטטוס ליד בידי ספק + היסטוריית ליד שכבר פותחו למרות דחייתם ל־V2 (#6/#12). לא משנים קוד/Scope על סמך ההכרה בפער.
2. **Legal + remaining Acceptance checks:** לאמת versioned `LEGAL_ACCEPTANCE` ו־Legal Release (#13); פעילות מתמשכת קיימת בקוד ובצילום DEV, ולבדוק את פרשנות ״שניהם״ אם עדיין נדרשת (#4/#8/#11). התאמה לחינוך מיוחד עברה ל־V2 ואינה חסם.
3. **QA ו־Release Evidence (P0):** למפות ממצאי #17 ו־#11 לגרסת פיתוח אמת; לבדוק Lead transitions, RLS, מחיקות היסטוריות, onboarding/Verified, 390×844/768/1280 ורגרסיה. אין לסמן PASS על סמך מסמכי הפיתוח בלבד.

### NEXT — תוכן ציבורי ומוכנות השקה
4. #19 + #20 — FAQ ו״מהי סלקט / איך זה עובד״ (לא נמצאו routes ייעודיים בקוד שסופק).
5. #23 + #18 — דף ספקים ומגזין; נדרש מיפוי תוכן, קופי ו־UX.
6. #10 + #13 — השלמת Legal/public copy מאושר, פרטי מפעיל, פרטיות, הסכמות ונתיבי דיווח.
7. #21 + #22 — SEO/social previews ו־Search → Program → Lead analytics לאחר אימות כללי פרטיות.
8. #11 — QA עצמאי סופי על Build מועמדת להשקה.
9. #2 — החלטת GO/NO-GO עם ראיות וסגירת כל P0.

### PARALLEL — עבודה עסקית
- #9 — First Supply: יעד 20–100 ספקים איכותיים; צילום הקוד מתעד ב־25.10.2026 אפס ספקים אמיתיים ב־Production **נכון לאותו תיעוד בלבד**. יש לבדוק היום מספר מאושרים/Verified/תוכניות וכיסוי קטגוריה×אזור×גיל; אין להסיק מצב עדכני מה־ZIP.
- #3–#8, #14–#16 — קיימים רכיבי קוד נרחבים, אך כל Issue פתוח דורש מיפוי Acceptance ו־Runtime Evidence לפני Done.

### חריגות מוצר שלא אושרו
- **Guest contact:** קוד ה־Signup Gate וה־DB מונעים Lead של אורח, בניגוד ל־Scope Lock.
- **Account profiles:** `guard_one_profile` מנוגד לתמיכה בכמה תפקידי משתמש.
- **Program metadata:** פעילות מתמשכת נמצאת בקוד והוצגה בצילום DEV; ייצוג ״שניהם״ במפורש טרם אומת. התאמה לחינוך מיוחד הועברה ל־V2 בהחלטת בעל המוצר.
- **GEFEN:** מידע קיים, תצוגה ציבורית מוסתרת עם `SHOW_GEFEN=false`.
- **V2 creep:** Supplier משנה Lead status ויש טבלת `lead_status_history`.
- **Legal:** חסרה עדות למנגנון `LEGAL_ACCEPTANCE` גרסאי; קיים consent timestamps בסיסי.
- **Verified references:** קיים אישור אדמין ידני; לא נמצא קישור המלצה חד־פעמי ל־14 יום.

### תנאי מעבר ל־Done
`Implemented in archive` ≠ `Runtime PASS` ≠ `Production verified`. לא סוגרים Issue/Launch Gate לפני בדיקה מול גרסת Build ו־DB מזוהות, ראיות, החלטת מוצר רשומה ו־QA עצמאית.

---

## Historical Plan — 2026-10-10 (נשמר למעקב)

### מטרה
להביא את סלקט ל-MVP יציב ומוכן להשקה בחיפה והצפון, עם היצע איכותי, חיפוש ויצירת קשר מקצה לקצה, Trust layer ברור, עמודים ציבוריים שלמים, Legal מוכן, QA ומדידה בסיסית.

### עכשיו
1. #17 — תיקונים אחרי QA, Retest ו-Regression.
2. #19 — דף שאלות ותשובות.
3. #20 — דף "מהי סלקט / איך זה עובד".

### אחר כך
4. #18 — עמוד המגזין.
5. #23 — דף לספקים / הצטרפו לסלקט.
6. #10 + #13 — Public Readiness + Legal MVP.
7. #21 — SEO, Social Sharing ו-Public Page Polish.
8. #22 — Analytics בסיסי.
9. #11 — Regression סופי.
10. #2 — Go / No-Go.

### במקביל
- #9 — First Supply והשלמת כיסוי.
- #3–#8 ו-#14–#16 — מיפוי מול מצב הפיתוח ברגע שתהיה גישת קריאה תקינה ל-repo של רואי.

## מה חוסם Launch
- P0 פתוח.
- Lead flow לא אמין.
- תקלה בהרשאות או פרטיות.
- פרסום Supplier / Program / Review בניגוד לכללים.
- Verified או GEFEN מוצגים באופן מטעה.
- Legal Release חסר במקום שבו הוא נדרש.
- Supply threshold שהוגדר לא הושג.
- Regression סופי לא עבר על גרסת המועמדת ל-Production.

## מסלולי עבודה

### Product & Discovery
#3 Discovery & Search, #4 Supplier & Programs, #5 Customer & Institution.

### Leads, Trust & Admin
#6 Lead Flow, #7 Admin, #14 Lead Reliability, #15 Verified Workflow.

### Data
#8 Schema Integrity, #16 Historical Integrity.

### Supply
#9 First Supply.

### Public Content
#18 Magazine, #19 FAQ, #20 About/How it works, #23 Suppliers landing page.

### Legal & Public Readiness
#10 Public Readiness, #13 Legal Integration.

### QA & Launch
#17 QA fixes, #11 E2E QA, #21 SEO/Public Polish, #22 Analytics, #2 Go/No-Go.

### Post Launch / V2
#12 Scope Guard.

## Definition of Done להשקה
MVP מוכן ל-Go רק כאשר:
- כל P0 סגורים.
- Search → Program → WhatsApp/Phone → Lead עובד end-to-end.
- פעולות Admin הקריטיות עובדות.
- schema, API ו-UI עקביים.
- Supply threshold הושג.
- FAQ, About/How it works ועמודי Legal מוכנים.
- QA עבר Mobile + Desktop.
- Regression עבר על אותה build שמיועדת להשקה.
- קיימת מדידת Search → Program → Lead בסיסית.
- התקבלה החלטת Go מפורשת.

## Backlog
- #1 Scope Lock — Done.
- #2 Launch Gate.
- #3 Discovery & Search.
- #4 Supplier & Programs.
- #5 Customer & Institution.
- #6 Lead Flow.
- #7 Admin Console.
- #8 Schema Integrity.
- #9 First Supply.
- #10 Public Readiness.
- #11 End-to-End QA.
- #12 V2 Scope Guard.
- #13 Legal MVP Integration.
- #14 Lead Reliability & Status Matrix.
- #15 Verified & Recommendation Workflow.
- #16 Historical Integrity.
- #17 QA fixes + Regression.
- #18 Magazine.
- #19 FAQ.
- #20 What is SELEKT / How it works.
- #21 SEO & Public Page Polish.
- #22 Launch Analytics.
- #23 Suppliers / Join SELEKT.

## היסטוריית החלטות תמציתית
### 2026-10-05
- Scope Lock ננעל.
- גפ"ן ברמת PROGRAM.
- Activity Format: חד-פעמי / מתמשך / שניהם.
- התאמה לחינוך מיוחד ברמת PROGRAM.
- Multi-region לספק.
- approval הופרד מ-SELEKT Verified.
- naming אחיד ל-Lead/Review.
- Legal MVP הוגדר כתנאי השקה.

### 2026-10-10
- נוספו QA fixes, Magazine, FAQ, About/How it works, SEO ו-Analytics.
- נוסף דף ייעודי לספקים.
- לכל Issue צורפו מסמכי מקור רלוונטיים מדרייב.
