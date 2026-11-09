# GitHub Project Setup — סלקט

## עדכון תפעולי — DEV בלבד (2026-11-09)

**המקור התפעולי הנוכחי:** [DEV Task Board](BOARD.md). בשלב זה מנהלים רק פיתוח, התאמה לאפיון ובדיקות ב־[selekt-dev.vercel.app](https://selekt-dev.vercel.app). Production/Launch לא נמדדים או מקודמים בבורד הפעיל.

**הבחנה חשובה:** קובץ זה מתאר כיצד להגדיר/לסדר את GitHub Projects האינטראקטיבי; חיבור GitHub הנוכחי מאפשר לערוך Issues ומסמכי repo, **לא** לעדכן ישירות את שדות ה־Projects (כמו Status/Column). אין להציג המלצת שיבוץ כסטטוס ששונה בפועל.

### תצוגת עבודה מוצעת — DEV MVP1
- **Project view:** `DEV — Current Work` (כאשר קיים שדה Environment: DEV בלבד; אחרת view ידני על פי רשימת Issues בבורד).
- **Columns / workflow:** `Backlog` → `Decision Needed` / `Ready` → `In Progress` → `Needs DEV Verification` → `Review / QA` → `Done`; `Deferred` בנפרד. אלו שמות מומלצים, לא שדות שהוגדרו בפועל.
- **Priority:** P0 עבור אי־התאמות קריטיות מול האפיון; P1 להשלמת תוכן ופוליש; P2 ל־V2.
- **Current focus:** החלטת Guest Contact (#6), Multi-role (#5/#8), הצגת GEFEN (#3/#4); בדיקת מימוש DEV בפועל (#3/#4/#7/#13/#15); QA ממוקד DEV (#17/#11).
- **Defer:** חינוך מיוחד ל־V2 (#12); #2 Launch Gate מחוץ לתצוגת DEV הפעילה.
- **Evidence field recommended:** `Code only` / `DEV observed` / `DEV tested` / `Blocked by environment`. אין לסמן Done על בסיס ZIP או screenshot בלבד.
- **No mutations:** אין שינוי בסטטוס Issues, Assignees, פיתוח או Production בעקבות מסמך זה.

---

## תכנון מקורי (היסטורי — מתייחס ל־Launch)

> מפרט מוכן להקמת ה-Project האינטראקטיבי. ה-Connector המחובר ל-ChatGPT אינו תומך כרגע ביצירה/עריכה של GitHub Projects, לכן הקובץ הזה מגדיר בדיוק את המבנה שעל ה-UI להכיל.

## Project
**Name:** סלקט — MVP & Launch

## Status
- Backlog
- Ready
- In Progress
- Review / QA
- Done

## Fields
### Priority
- P0
- P1
- P2

### Workstream
- Product
- Dev
- Suppliers
- Content
- Legal
- QA
- Data
- Launch
- Analytics

### Phase
- MVP
- Launch
- Post Launch

### Blocked
- Yes
- No

### Owner
GitHub assignee / text לפי הצורך.

## Views

### 1. Board — Main
Group by: Status  
Sort by: Priority  
Filter: Phase != Post Launch

### 2. Launch Blockers
Filter:
- Priority = P0
- Status != Done

### 3. Public Readiness
Filter Workstream:
- Content
- Legal
- Launch

### 4. QA
Filter Workstream = QA

### 5. Supply
Filter Workstream = Suppliers

### 6. Post Launch
Filter Phase = Post Launch

## Initial placement

### Done
- #1 Scope Lock

### In Progress / Current focus
- #17 QA fixes
- #19 FAQ
- #20 What is SELEKT / How it works

### Ready
- #18 Magazine
- #23 Suppliers / Join SELEKT
- #10 Public Readiness
- #13 Legal MVP Integration
- #21 SEO / Social Sharing / Public Polish
- #22 Launch Analytics
- #9 First Supply

### Needs dev-state audit before choosing final status
- #3 Discovery & Search
- #4 Supplier & Programs
- #5 Customer & Institution
- #6 Lead Flow
- #7 Admin Console
- #8 Schema Integrity
- #14 Lead Reliability
- #15 Verified Workflow
- #16 Historical Integrity

### Review / QA later
- #11 End-to-End QA

### Final gate
- #2 Go / No-Go

### Post Launch
- #12 V2 Scope Guard

## Priority map
### P0
#2, #3, #4, #6, #7, #8, #9, #10, #11, #13, #14, #15, #16, #17, #19, #20

### P1
#5, #18, #21, #22, #23

### P2
#12

## Rule
ה-Project הוא שכבת תצוגה וניהול בלבד. ה-Issue נשאר מקור האמת למשימה, והמסמכים בדרייב נשארים מקור התוכן/אפיון המתאים.
