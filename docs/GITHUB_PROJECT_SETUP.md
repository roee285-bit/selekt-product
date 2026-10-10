# GitHub Project Setup — סלקט

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
