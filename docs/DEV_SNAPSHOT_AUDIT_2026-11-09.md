# SELEKT — ביקורת סטטית של קוד השותף (9.11.2026)

## תיקון ביקורת — החלטת בעל המוצר מ־2026-11-09

1. **חינוך מיוחד:** הוחלט במפורש שאינו נדרש בהשקה הראשונית. אי־מציאת `special_education_fit` בארכיון נשארת ממצא טכני, אך **אינה פער MVP/P0 או חסם Launch**; לשייך ל־V2 ול־#12.
2. **פעילות מתמשכת:** צילום מסך DEV שנמסר על ידי בעל המוצר תואם לקוד: `web/src/app/supplier/programs/program-form.tsx:65-75` כולל checkbox, תדירות, משך מפגש ומספר משתתפים; `web/src/app/supplier/actions.ts:45,67-71` שומר אותם; `web/src/app/programs/[id]/page.tsx:84-88` מציג. לפיכך **מימוש פעילות מתמשכת קיים**, ואין להציגה כחסרה. השדה `is_ongoing` בוליאני; ייצוג פורמלי של האפשרות ״שניהם״ לפי Scope Lock **טרם אומת** וטעון Acceptance, לא כישלון מוכח של DEV.
3. **סביבות:** לא נפתח DEV או PROD בפועל; הביקורת היא ZIP סטטי בתוספת צילום מסך שסיפק המשתמש. אין ראיית Deployment/Runtime כלשהי.

> תיקון זה גובר על השורות ההיסטוריות בטבלת הפערים להלן לגבי דירוג חומרה ומצב שני הנושאים; הטבלה המקורית נשמרה לצורך עקיבות.

---

**מקור:** ארכיון `selekt-main.zip` שהועלה לשיחה ב־2026-11-09; שורש הקוד `selekt-main/`.
**זמן מצב המתועד בקוד:** `HANDOFF.md`, `CHANGELOG.md`, `sessions/2026-10-25.md` — עד 2026-10-25.
**מגבלה:** הארכיון אינו כולל `.git`, SHA מאומת, סודות סביבת ריצה או גישה ל־Supabase/Vercel. לא הורצו build, migrations, tests או E2E; לא נבדקה Production. הצהרות "merged/live" הן הצהרות בקובצי הפיתוח, **לא אימות עצמאי**.
**מקור אמת מוצרי:** האפיון הראשי + [Scope Lock 2026-10-05](SCOPE_LOCK_2026-10-05.md). מסמך זה **אינו משנה** החלטת מוצר/Scope Lock.

## נמצא בקוד — מימוש קיים, ללא הוכחת Runtime

| תחום | ראיה בארכיון | סטטוס |
|---|---|---|
| אפליקציית Web | `web/package.json`, `web/src/app/` — Next.js/React/TypeScript/RTL | קיים בקוד |
| Schema ו־RLS | `supabase/migrations/` — 35 קובצי SQL; `supabase/tests/` — 5 קובצי בדיקות | קיים בקוד; החלת migrations והרצה לא אומתו |
| הרשמה/כניסה/Google | `web/src/app/signup/`, `login/`, `onboarding/`, `auth/` | קיים בקוד |
| מסלול ספק ותוכניות | `web/src/app/join/`, `supplier/` | קיים בקוד |
| Discovery, מסננים, אזורי שירות מרובים | `web/src/app/search/page.tsx`, `web/src/lib/search.ts`, `web/src/app/suppliers/[id]/`, `web/src/app/programs/[id]/` | קיים בקוד |
| מועדפים, פניות, ביקורות | `web/src/app/account/`, `web/src/components/favorite-button.tsx` | קיים בקוד |
| Admin/Verified/Media review | `web/src/app/admin/`, `supabase/migrations/20261015000022_verified_rules.sql` | קיים בקוד |
| Lead dedup + rate limit | `supabase/migrations/20260930000012_lead_rate_limit.sql`, `20261025000034_contact_gate_db.sql` | קיים בקוד, התנהגות בזמן ריצה לא אומתה |
| Tracking/consent scaffold, SEO | `web/src/lib/privacy/`, `web/src/app/robots.ts`, `sitemap.ts` | קיים בקוד; GA4 ב־Production לא אומת |
| בדיקות frontend | `web/tests/` — CSP, phone, privacy, search | קבצים קיימים; לא הורצו |

## פערים מול Scope Lock — דרושות הכרעות/תיקון

| עדיפות בדיקה | נושא / Issue | ראיית קוד | פער ומצב |
|---|---|---|---|
| P0 — החלטת מוצר | #6, #3, #11: Lead של אורח | `web/src/app/programs/[id]/actions.ts` מחזיר `sign_in`; `20261025000034_contact_gate_db.sql` מעלה `sign_in_required`; `web/src/components/contact-gate.tsx` | אורח יכול לחפש אך לא לחשוף פרטי קשר/ליצור Lead. **סותר את ה־MVP** שמאפשר Lead אורח; לא לפתור אוטומטית בלי החלטה |
| P0 — חסר ב־MVP | #4, #8, #11: התאמה לחינוך מיוחד | לא נמצא `special_education_fit` בסכמות/טופס/תצוגות `program` | להגדיר `not_specified/suitable/not_suitable` ותג ברמת Program; Requires implementation + QA |
| P0 — חסר ב־MVP | #4, #8, #11: Activity Format | `web/src/app/supplier/programs/program-form.tsx` + `web/src/app/supplier/actions.ts` משתמשים ב־`is_ongoing` בלבד | אינו מייצג מפורשות שלושה מצבים: חד־פעמי / מתמשך / שניהם |
| P0 — החלטת מוצר | #5, #8, #11: Multi-role account | `supabase/migrations/20261017000026_post_qa_data_rules.sql` `guard_one_profile`; `web/src/app/onboarding/page.tsx` | קוד אוכף פרופיל עסקי אחד לחשבון; Scope Lock מחייב אפשרות לכמה פרופילי תפקיד |
| P0 — פער משפטי | #13: Legal acceptance | `20261005000013_account_consents.sql`, `20261005000014_supplier_wizard_fields.sql` | קיימות חותמות הסכמה, אך לא נמצא `LEGAL_ACCEPTANCE` לפי document_key/version_id/accepted_at/context; נדרשת התאמה ל־Legal Release |
| P0 — חסר ציבורי | #19, #20; #18/#23 בהמשך | מפת routes תחת `web/src/app/` | אין routes ייעודיים שנמצאו ל־FAQ, About/How it works, Magazine, Join Suppliers; יש מסכי הרשמה קיימים, לא עמודי הסבר אלה |
| P0/P1 — טעון הכרעה | #3, #4, #10: GEFEN | `web/src/lib/labels.ts`: `SHOW_GEFEN = false`; הגדרת Program נשמרת | מנגנון הנתונים קיים אך הממשק הציבורי מוסתר. לא להפוך flag ללא החלטת מוצר |
| P1 — חריגת Scope | #6, #12, #14: Supplier lead status + history | `20261022000029_supplier_lead_status.sql`, `20261022000030_lead_status_history.sql`; `CHANGELOG.md` | קיים פיתוח ש־Scope Lock דוחה ל־V2. דרוש תיעוד החלטה והערכות הרשאות/התנהגות, לא מחיקה אוטומטית |
| P1 — פער בהליך אימות | #15: Recommendation workflow | `web/src/app/join/references-fields.tsx`, `web/src/app/admin/actions.ts` | קיים הזנת ממליצים ואימות Admin ידני; לא נמצא קישור להגשה חד־פעמית שתוקפו 14 יום כמוגדר ב־Scope Lock |
| P0 — Legal/Launch | #10, #13, #2 | `TODO.md`, `HANDOFF.md`; routes `privacy/terms/cookies/supplier-terms` | מסמכי Legal מוגדרים כטיוטות לפי Snapshot, ויש השלמות מפעיל/אישור עו״ד נדרשות. לא אומת סטטוס נוכחי |
| P0 — Supply | #9, #2 | `HANDOFF.md` מציין שב־2026-10-25 אין ספקים אמיתיים בפרודקשן | מצב היצע נוכחי אינו ידוע. יש לאמת 20–100 איכותיים וכיסוי קטגוריה×אזור×גיל טרם קמפיין ביקוש |

### בדיקות פתוחות / סיכונים נוספים

- **#14:** יש מנגנוני duplicate/rate-limit ו־status, אך יש לאשר transition matrix מלאה ולבדוק פעולות מותרות/אסורות; `supplier_set_lead_status` מאפשר לספק לעדכן את הסטטוס של הליד שלו.
- **#16:** `lead.program_id` הוגדר במקור עם `ON DELETE CASCADE`. יש לוודא שאין מחיקה קשיחה של תוכנית שמוחקת היסטוריית Leads/Reviews; היעדר שימוש ב־hard delete ב־UI אינו מוכיח הגנה במסד.
- **#15:** Verified קיים ואינו זהה לאישור ספק, אך התאמתו לזרימת ההמלצות הנעולה דורשת QA מול DB עובד.
- **#17/#11:** קובצי `TODO.md` ו־`CHANGELOG.md` מדווחים על תיקונים ובדיקות עבר. בדיקת QA עצמאית ל־390×844/768/1280 וה־Production candidate האחרון **לא בוצעה כאן**; החסם הסביבתי הקודם לא ייחשב Failure של האפליקציה.
- **#21/#22:** SEO בסיסי קיים בקוד. Full public pages/analytics launch tracking ועמידה במגבלות הפרטיות טעונים אימות.
- **#2:** טענת `HANDOFF.md` על Production/35 migrations אינה מחליפה בדיקת production DB, rollout ו־Go/No-Go.

## סדר פעולות מומלץ — ללא שינוי ה־Scope אוטומטי

1. **Product decision gate:** לסגור במפורש Guest Contact, Multi-role, GEFEN, Supplier status/history; לתעד החלטות מאושרות ב־Decision Log וליישר אפיון/Issues לפני שינוי קוד.
2. **P0 technical gaps:** Activity Format (3 מצבים), Special Education, Versioned Legal Acceptance; לבדוק גם deletion/historical integrity והרשאות.
3. **Public readiness:** FAQ, About/How it works, Suppliers page, Magazine; תוכן משפטי ומיתוג לפי תנאים מאושרים.
4. **Supply + measurement:** אימות בפועל של ספקים אמיתיים, צפיפות לפי קטגוריה/אזור/גיל ומדדי Search → Program → Lead בהתאם להסכמה.
5. **Independent QA:** לבדוק קוד/DB מותקנים ומועמד גרסה ב־mobile/tablet/desktop, כולל Regression, Legal, Trust ו־Leads.
6. **Launch Gate #2:** להחליט GO רק עם Evidence, 0 P0 פתוחים ו־Supply threshold מאושר.

**Policy:** אין לסגור Issues, לסמן GO, לשנות Scope Lock או להציג מוצר כ־Production-ready על בסיס ZIP בלבד.
