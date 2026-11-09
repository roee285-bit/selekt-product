# סלקט — Launch Board

> מעודכן ל־2026-11-09 על בסיס ביקורת סטטית של ארכיון קוד השותף (הארכיון מתעד פיתוח עד 2026-10-25). [דוח הפערים והראיות](DEV_SNAPSHOT_AUDIT_2026-11-09.md) · [תוכנית העבודה](WORKPLAN.md) · [Scope Lock](SCOPE_LOCK_2026-10-05.md).

**Status:** RELEASE READINESS NOT VERIFIED / NO-GO להחלטת השקה על סמך הראיות הזמינות בלבד. זה אינו קביעה ש־Production נכשל; לא בוצעה בדיקת Runtime עדכנית.

## NOW — מיקוד נוכחי (3 שערים)

1. **Product decisions — P0:** [#6 Guest Lead](https://github.com/roee285-bit/selekt-product/issues/6), [#5/#8 Multi-role](https://github.com/roee285-bit/selekt-product/issues/8), [#3 GEFEN](https://github.com/roee285-bit/selekt-product/issues/3), [#12 Supplier status/history V2](https://github.com/roee285-bit/selekt-product/issues/12). סתירות בין הקוד ל־Scope Lock; **דרוש אישור, אין שינוי החלטה אוטומטי**.
2. **Missing MVP fields / Legal — P0:** [#4 Program](https://github.com/roee285-bit/selekt-product/issues/4), [#8 Schema](https://github.com/roee285-bit/selekt-product/issues/8), [#13 Legal](https://github.com/roee285-bit/selekt-product/issues/13). Activity Format (3 מצבים), התאמה לחינוך מיוחד, versioned Legal Acceptance; בדיקת Verified links.
3. **Release evidence + QA — P0:** [#17 QA fixes](https://github.com/roee285-bit/selekt-product/issues/17), [#11 E2E](https://github.com/roee285-bit/selekt-product/issues/11), [#14 Leads](https://github.com/roee285-bit/selekt-product/issues/14), [#16 Integrity](https://github.com/roee285-bit/selekt-product/issues/16). בדיקות על Build/DB מזוהים, Regression מלא, מובייל/טאבלט/דסקטופ; אין להמיר חסם Browser בכישלון אפליקציה.

## NEXT — השלמת עמודים ציבוריים ושער השקה

- [#19 — FAQ](https://github.com/roee285-bit/selekt-product/issues/19) + [#20 — מהי סלקט / איך זה עובד](https://github.com/roee285-bit/selekt-product/issues/20): לא נמצאו נתיבי עמוד ייעודיים בארכיון.
- [#23 — דף הצטרפות לספקים](https://github.com/roee285-bit/selekt-product/issues/23) + [#18 — מגזין](https://github.com/roee285-bit/selekt-product/issues/18): לא נמצאו routes ייעודיים.
- [#10 — Public/Legal](https://github.com/roee285-bit/selekt-product/issues/10) + [#13 — Legal integration](https://github.com/roee285-bit/selekt-product/issues/13): פרטי מפעיל, נוסחים מאושרים והסכמות.
- [#21 — SEO & Social](https://github.com/roee285-bit/selekt-product/issues/21) + [#22 — Analytics](https://github.com/roee285-bit/selekt-product/issues/22): יסודות קיימים בקוד; השלמה ואימות השקה נדרשים.
- [#11 — E2E & Regression](https://github.com/roee285-bit/selekt-product/issues/11) → [#2 — Go/No-Go](https://github.com/roee285-bit/selekt-product/issues/2): רק לאחר ראיות לכל שער.

## PARALLEL — Supply

- [#9 — First Supply](https://github.com/roee285-bit/selekt-product/issues/9): להשיג ולוודא יעד מאושר של 20–100 ספקים איכותיים, עם צפיפות קטגוריה×אזור×גיל. הארכיון מתעד אפס ספקים אמיתיים ב־Production נכון ל־2026-10-25; **אין מכאן מידע על המצב הנוכחי**.

## IMPLEMENTED IN SNAPSHOT — עדיין לא Done

- [#3 Search](https://github.com/roee285-bit/selekt-product/issues/3), [#4 Supplier/Programs](https://github.com/roee285-bit/selekt-product/issues/4), [#5 Customers](https://github.com/roee285-bit/selekt-product/issues/5), [#6 Leads](https://github.com/roee285-bit/selekt-product/issues/6), [#7 Admin](https://github.com/roee285-bit/selekt-product/issues/7), [#8 DB](https://github.com/roee285-bit/selekt-product/issues/8), [#14 Reliability](https://github.com/roee285-bit/selekt-product/issues/14), [#15 Verified](https://github.com/roee285-bit/selekt-product/issues/15), [#16 Integrity](https://github.com/roee285-bit/selekt-product/issues/16).
- נמצאו App, Routes, RLS, 35 migrations ו־5 קובצי SQL tests. יש חפיפה משמעותית למוצר, אך חסרים/סותרים חלקי Scope; לא בוצע E2E חי, build או בדיקת Production. סטטוסי Issues הקיימים נשארים ללא שינוי.

## DONE — Product scope only

- [x] [#1 — MVP Scope Lock](https://github.com/roee285-bit/selekt-product/issues/1) — baseline החלטות, **לא הוכחת מימוש**.

## PARKING LOT

- [#12 — V2 Scope Guard](https://github.com/roee285-bit/selekt-product/issues/12). לא מוסיפים/מסירים Scope ללא אישור מפורש; יכולת V2 שקיימת בקוד אינה אישור להפעילה.

## כללי בקרה

1. `Exists in ZIP` / `Reported by developer` / `Runtime PASS` / `Production verified` הם מצבי ראיות שונים.
2. אין לסמן Done על סמך archive או CHANGELOG בלבד, ואין לסגור Launch Gate ללא בעלים מאשר.
3. P0 פתוח או אי־התאמה לא מאושרת בתחום Leads/Legal/Trust/Permissions/Program metadata חוסם הכרזת GO.
4. כל סתירת Scope מחייבת Decision Log לפני שינוי באפיון, בקוד או בקריטריוני QA.
5. מספר הספקים, ההיתכנות המסחרית והמצב החי של ההשקה אינם ניתנים להסקה מהארכיון.
