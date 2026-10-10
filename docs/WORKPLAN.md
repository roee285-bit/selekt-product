# סלקט — תוכנית עבודה MVP → Launch

> זהו מסמך Delivery. הוא מתרגם את אפיון המוצר לתוכנית ביצוע ואינו מחליף את האפיון הראשי.

## יעד
להביא את סלקט ל-MVP עובד ומוכן להשקה בחיפה והצפון, עם היצע איכותי ראשוני, חוויית חיפוש/יצירת קשר מלאה, יכולת ניהול אדמין, QA ותנאי Go/No-Go ברורים.

## מסלולי עבודה

### 1. Product / Scope
- לנעול Scope ל-MVP מול האפיון הראשי.
- ליישב שינויים שאושרו אחרי גרסת האפיון הקיימת.
- להגדיר Launch Gate וקריטריוני קבלה.

### 2. Discovery & Search
- Home + Hero + Search.
- פילטרים: קטגוריה, אזור, גיל, סוג אירוע, גפ"ן.
- Inspiration Chips קבועים וניתנים לניהול.
- עמודי ספק ותוכנית.
- אין Free-text LLM search ב-MVP.

### 3. Supplier
- הרשמה ועריכת פרופיל.
- ניהול תוכניות.
- SELEKT Verified לפי כללי האפיון.
- ייצוג גפ"ן ברמת התוכנית/הספק בהתאם להחלטה המאושרת.
- Dashboard בסיסי להצגת לידים בלבד.

### 4. Customer / Institution
- גלישה וחיפוש כאורח.
- הרשמה לפרטי / מוסד.
- מועדפים.
- ביקורת רק לאחר ליד שנסגר כזכייה ובאישור אדמין.

### 5. Leads
- WhatsApp + הצגת טלפון מייצרים Lead.
- תמיכה באורח ובמשתמש רשום.
- סטטוס ליד מנוהל באדמין ב-MVP.

### 6. Admin
- אישור/דחיית ספקים.
- Verified.
- ביקורות.
- LOV + Inspiration Chips.
- ניהול סטטוס לידים.

### 7. Data
- ACCOUNT + profiles.
- PROGRAM.
- LEAD / REVIEW / FAVORITE.
- LOV / INSPIRATION_CHIP.
- טבלאות interests.
- Constraints ו-FKs לפי האפיון.

### 8. Supply readiness
- First Supply לפני יצירת ביקוש אקטיבי.
- יעד ההשקה לפי האפיון: 20–100 ספקים איכותיים.
- מעקב אחר verified / completeness / coverage לפי קטגוריות ואירועים.

### 9. Content / Legal / Launch
- FAQ וטקסטים ציבוריים תואמים מוצר.
- מסמכים משפטיים מאושרים לפרסום.
- תוכן השקה בסיסי.
- Analytics / measurement מינימלי להשקה.
- Go/No-Go מסודר.

## סדר ביצוע מומלץ

### Phase A — Scope lock
1. יישור קו בין האפיון הראשי לבין החלטות חדשות.
2. הגדרת Launch Gate.
3. זיהוי כל P0 blockers.

### Phase B — Core product completion
1. Discovery/Search.
2. Supplier + Programs.
3. Customer/Institution.
4. Leads.
5. Admin.
6. Data integrity.

### Phase C — Launch readiness
1. Supply readiness.
2. QA end-to-end.
3. Legal/content.
4. Measurement.
5. Go/No-Go.

### Phase D — Post launch
רק אחרי השקה ונתונים אמיתיים: פריטי V2 כגון LLM search, dashboard מתקדם, personalization, dynamic chips, payments ו-lead status history.

## Definition of Done להשקה
MVP ייחשב מוכן רק כאשר:
- כל P0 סגורים.
- ה-flow מחיפוש → ספק/תוכנית → יצירת Lead עובד end-to-end.
- פעולות האדמין הקריטיות עובדות.
- אין פער ידוע בין schema לבין התנהגות המוצר.
- יש היצע התחלתי מספק להשקה.
- Legal/public copy מוכנים.
- QA עבר על mobile ו-desktop.
- התקבלה החלטת Go מפורשת.


## Backlog פעיל ב-GitHub
- #1 — Scope Lock: ליישב את האפיון הראשי עם החלטות מאוחרות.
- #2 — Launch Gate / Go-No-Go.
- #3 — Discovery & Search.
- #4 — Supplier & Programs.
- #5 — Customer & Institution.
- #6 — Lead Flow.
- #7 — Admin Console.
- #8 — Schema Integrity.
- #9 — First Supply.
- #10 — Public Readiness: Content / Legal.
- #11 — End-to-End QA.
- #12 — V2 Parking Lot / Scope Guard.

## סדר עדיפות לביצוע כרגע
1. #1 Scope Lock — **הושלם וננעל ב-2026-10-05**.
2. #2 Launch Gate.
3. במקביל: #3, #4, #6, #7, #8 לפי מצב הפיתוח בפועל.
4. #9 Supply readiness מתקדם במקביל לפיתוח.
5. #10 + #11 לפני Go/No-Go.


## Scope Lock — עדכון 2026-10-05
ה-baseline המחייב נמצא ב-[SCOPE_LOCK_2026-10-05.md](SCOPE_LOCK_2026-10-05.md).

Issues חדשים שנפתחו בעקבות ה-Gap Analysis:
- #13 — Legal MVP Integration.
- #14 — Lead Reliability & Status Matrix.
- #15 — Verified Completeness & Recommendation Workflow.
- #16 — Historical Integrity: ratings, inactive LOV, deletion & guest leads.
- #17 — QA fixes + regression.
- #18 — Magazine page.
- #19 — FAQ page.
- #20 — What is SELEKT / How it works.
- #21 — SEO & public page polish.
- #22 — Launch analytics.

ה-Scope Lock עדכן גם את #3, #4, #6, #7, #8, #9, #10, #11 ו-#12.


## עדכון תוכנית עבודה — 2026-10-10

### QA וייצוב לפני השקה
- #17 — תיקונים אחרי סבב QA + Retest + Regression מלא.
- #11 נשאר שער ה-QA הכולל; #17 מרכז את התיקונים עצמם.
- אין Launch עם P0 QA פתוח.

### עמודים ציבוריים שחייבים להשלים
- #18 — עמוד המגזין של סלקט.
- #19 — דף שאלות ותשובות.
- #20 — דף "מהי סלקט / איך זה עובד".
- #21 — SEO, Social Sharing ו-Public Page Polish.

### מדידת ההשקה
- #22 — Analytics בסיסי: Search → Program → Lead + Zero Results.

### סדר ביצוע מעודכן
1. לסגור תיקוני QA ב-#17.
2. להשלים את עמודי הציבור הקריטיים: #19 ו-#20.
3. להשלים את עמוד המגזין #18.
4. להשלים Legal/Public Readiness דרך #10 ו-#13.
5. להשלים SEO ושיתוף #21.
6. לוודא מדידה בסיסית דרך #22.
7. להריץ Regression סופי דרך #11.
8. לבצע Go/No-Go לפי #2.

### דברים שלא נשכחו וכבר מנוהלים ב-Backlog
- מסמכים משפטיים, פרטיות, consent, דיווח וסגירת חשבון — #13.
- Supplier / Program / Verified — #4 ו-#15.
- Leads — #6 ו-#14.
- Supply readiness — #9.
- Data integrity — #8 ו-#16.
- Launch Gate — #2.
