# סלקט — DEV Task Board

**עודכן:** 2026-11-09  
**סביבה פעילה לניהול:** [SELEKT DEV](https://selekt-dev.vercel.app/) בלבד.  
**מאגר ניהול:** `roee285-bit/selekt-product`. **מאגר קוד:** `royrozen/selekt` — לא נגיש ישירות דרך החיבור הנוכחי; תמונת קוד קיימת בארכיון `selekt-main.zip`.  
**מקורות:** [תוכנית העבודה](WORKPLAN.md), [תצפית DEV](DEV_HOME_READONLY_2026-11-09.md), [סקירת קוד סטטית](DEV_SNAPSHOT_AUDIT_2026-11-09.md), [Scope Lock והעדכון מ־2026-11-09](SCOPE_LOCK_2026-10-05.md).

> **מטרת הבורד כרגע:** לדעת מה קיים בקוד, מה נצפה ב־DEV ומה חסר אישור או בדיקה. אין להסיק מצב Production, אין להריץ תהליכים ב־Production, ואין לקדם כאן Launch GO/NO-GO. הבורד אינו אישור לשינוי קוד.

## NOW — שלושה מוקדים בלבד

### 1. החלטות מוצר לפני עבודה נוספת — DECISION NEEDED
- [#6 — Lead לאורח](https://github.com/roee285-bit/selekt-product/issues/6): ה־ZIP מחייב התחברות ליצירת קשר, בניגוד ל־Scope Lock. **החלטת מוצר נדרשת**; התנהגות אורח ב־DEV טרם נבדקה.
- [#5 — Multiple roles](https://github.com/roee285-bit/selekt-product/issues/5) + [#8 — Data/Schema](https://github.com/roee285-bit/selekt-product/issues/8): בקוד קיים `guard_one_profile` מול דרישת מספר תפקידים לאותו חשבון. **פער קוד–אפיון**, לא כישלון DEV מוכח.
- [#3 — GEFEN](https://github.com/roee285-bit/selekt-product/issues/3) + [#4 — תוכניות](https://github.com/roee285-bit/selekt-product/issues/4): `SHOW_GEFEN=false` בארכיון; לברר אם ההסתרה מכוונת בשלב DEV ואילו בדיקות נדרשות.
- [#12 — Scope Guard](https://github.com/roee285-bit/selekt-product/issues/12): מנגנוני עדכון סטטוס ליד בידי ספק והיסטוריית לידים קיימים ב־ZIP אף שנדחו ל־V2. לא לשנות Scope ללא החלטה.

### 2. מיפוי מימוש מול DEV — NEEDS DEV VERIFICATION
- [#3 — Discovery/Search](https://github.com/roee285-bit/selekt-product/issues/3): **נצפו** Home, חיפוש, קטגוריות, כרטיסי ספקים ותוכניות. **לא נבדקו** תוצאות חיפוש, פילטרים וניווט מלא.
- [#4 — Supplier/Programs](https://github.com/roee285-bit/selekt-product/issues/4): **נצפו בצילום DEV של בעל המוצר** פעילות מתמשכת, תדירות, משך ומספר משתתפים; הקוד כולל שדות ושמירה. בדיקות שמירה חיות לא בוצעו. לבדוק רק אם מצב ״שניהם״ נדרש במפורש.
- [#6 — Lead Flow](https://github.com/roee285-bit/selekt-product/issues/6) + [#14 — Lead Reliability](https://github.com/roee285-bit/selekt-product/issues/14): לבדוק את התנהגות ה־CTA וה־sign-in gate בסשן אורח **ללא שליחת ליד**; אחר כך לתכנן בדיקות כתיבה עם אישור נפרד.
- [#7 — Admin](https://github.com/roee285-bit/selekt-product/issues/7) + [#15 — Verified](https://github.com/roee285-bit/selekt-product/issues/15): בדף הבית המחובר הופיע קישור Admin ותגי Verified. פעולות וזרימת המלצות **לא נבדקו**.
- [#13 — Legal](https://github.com/roee285-bit/selekt-product/issues/13) + [#16 — Data integrity](https://github.com/roee285-bit/selekt-product/issues/16): קיימים רכיבי קוד, אך consent גרסאי, הגנות מחיקה ושמירה על היסטוריה דורשים אימות ברמת DB/API.

### 3. QA ממוקד DEV — QA / BLOCKED BY ACCESS
- [#17 — QA defects & retest](https://github.com/roee285-bit/selekt-product/issues/17) ו־[#11 — E2E QA](https://github.com/roee285-bit/selekt-product/issues/11).
- בדיקות יעד: desktop ו־viewport `390×844`, `768`, `1280`; זרימות Guest/Search, User, Supplier ו־Admin; השלמות Legal/Privacy והרשאות.
- **מצב ראיות:** עמוד הבית נצפה באמצעות קריאת לשונית מחוברת בלבד, ללא ניווט/לחיצה. לא בוצעו מבחני responsive או E2E ב־DEV. מגבלת כלי הבדיקה אינה FAIL של המוצר.
- **כלל:** Retest/Regression רק מול גרסת DEV מזוהה. אין הרשאה לכתיבה עסקית, הרשמה, יצירת ליד או שינוי חשבונות בבדיקה הזו.

## NEXT — מוכן לאפיון/פיתוח ב־DEV (לא אומת כמיושם)

- [#19 — FAQ](https://github.com/roee285-bit/selekt-product/issues/19), [#20 — מהי סלקט / איך זה עובד](https://github.com/roee285-bit/selekt-product/issues/20): דרושים נתיבים, תוכן וקופי; לא נמצאו עמודי route ייעודיים בארכיון שנבדק.
- [#23 — דף לספקים](https://github.com/roee285-bit/selekt-product/issues/23), [#18 — מגזין](https://github.com/roee285-bit/selekt-product/issues/18): דרישות תוכן ועיצוב ב־DEV, לא להניח שאין מימוש חדש מאז צילום הקוד.
- [#10 — Public copy](https://github.com/roee285-bit/selekt-product/issues/10) + [#13 — Legal integration](https://github.com/roee285-bit/selekt-product/issues/13): בעמוד הבית קיימים קישורים משפטיים, אך תוכן, גרסאות הסכמה וזרימות טרם אומתו.
- [#21 — SEO/social](https://github.com/roee285-bit/selekt-product/issues/21), [#22 — Analytics](https://github.com/roee285-bit/selekt-product/issues/22): קוד בסיסי קיים; בדיקות DEV מול תרחישים ואירועי מדידה עדיין נדרשות.

## PARALLEL — נתונים ו־Supply בסביבת DEV

- [#9 — First Supply](https://github.com/roee285-bit/selekt-product/issues/9): ב־DEV נצפו ספקים ותוכניות, כולל רשומות QA. יש להבדיל בין נתוני דמה לבין ספקים אמיתיים; אין להסיק מכך עמידה ביעד המסחרי 20–100.

## DONE — החלטות בלבד, לא בדיקת מערכת
- [#1 — MVP Scope Lock](https://github.com/roee285-bit/selekt-product/issues/1) — החלטת אפיון נעולה, עם עדכון מאושר מ־2026-11-09.

## DEFERRED — לא ב־DEV MVP1
- [#12 — V2 Parking Lot](https://github.com/roee285-bit/selekt-product/issues/12): **חינוך מיוחד** (החלטת בעל המוצר מ־2026-11-09); יחד עם יתר פיצ'רי V2. פעילות מתמשכת **לא** נדחתה, ומומשה בממשק לפי צילום ו־ZIP.
- [#2 — Launch GO/NO-GO](https://github.com/roee285-bit/selekt-product/issues/2): נשאר רשום להמשך, אך **מחוץ למיקוד הבורד הנוכחי**. אין החלטת השקה כעת.

## מפתח סטטוסים ואיכות ראיות

- **Decision Needed:** נדרשת הכרעת בעל המוצר לפני שינוי Scope או קוד.
- **Ready for DEV:** מוגדר מה צריך לבנות או להשלים, אך לא סומן Done.
- **Needs DEV Verification:** קיים קוד/ממשק, טרם עבר בדיקה אינטראקטיבית מלאה בסביבת DEV.
- **QA / Blocked by Access:** לא ניתן להשלים בדיקה עקב כלי/סשן/רשת; לא מסווגים כאפליקציה שנכשלה.
- **Done:** רק לאחר Acceptance + ראיה מהגרסה המתאימה, ללא הנחות על סמך קובץ ZIP.
- **Deferred:** מחוץ לשלב DEV MVP1 הנוכחי.

**כלל ניהול:** `Source code exists` ≠ `DEV UI observed` ≠ `DEV functionality passed`. אין לשנות סטטוס Issues או שדות GitHub Project ללא ראיית בדיקה או הנחיית בעל המוצר. מסמך זה הוא Board תיעודי; הוא אינו סנכרון אוטומטי עם GitHub Projects האינטראקטיבי.
