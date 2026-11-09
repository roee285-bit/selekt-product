# SELEKT — DEV Home Read-Only Observation | 2026-11-09

**Target:** https://selekt-dev.vercel.app/
**Source/evidence:** Browser read-only inspection of an already-open connected tab titled `סלקט | פעילויות ונותני שירות למוסדות חינוך` on 2026-11-09, compared with supplied `selekt-main.zip` (snapshot documented through 2026-10-25).
**Session:** The tab was **authenticated** (account/admin/supplier navigation visible). This is *not* a guest session. No user-identifying account data has been copied into this report.
**Actions:** Read page context only. Did **not** click controls, follow links, submit forms, create Leads, write business data, run tests or access Production.

## Observed directly on DEV homepage
- Hebrew RTL home with hero `כל הפעילויות במקום אחד`, text search input and category/chip links.
- Category cards with displayed program counts; multiple recent program cards link to `/programs/[id]`.
- `נותני שירות מאומתים` section displaying suppliers and `סלקט Verified` badges; links to `/suppliers/[id]`.
- Link destinations for `/search`, `/supplier`, `/admin`, `/account` appear in this authenticated session.
- Public footer links to `/accessibility`, `/privacy`, `/terms`, `/cookies` and cookie settings control. **Link presence ≠ route acceptance/legal compliance verified.**
- Examples visibly named as QA/test data (`מופע תיאטרון E2E QA1 ערוך`, `ספק נקי QA Round 3`). Appropriate in DEV; before launch, verify these are not public on Production or counted as genuine supply.

## Comparison to partner ZIP
- `web/src/app/page.tsx` contains home search, categories, recent programs and Verified supplier queries, which matches the observed home layout.
- `web/src/app/search/page.tsx` uses search terms/`search_programs`; presence of a text search UI is **not** evidence of LLM search. Interactive search filters/results have **not** been exercised.
- `web/src/lib/labels.ts` has `SHOW_GEFEN = false`; no assumption made about current DEV/PROD config, although the supplied ZIP hides GEFEN.
- Supplier's ongoing-program form in ZIP, plus user-provided DEV screenshot, show checkbox, frequency, session minutes and participant fields. Saving and edge cases on live DEV were **not** exercised.
- ZIP `web/src/app/programs/[id]/actions.ts` requires sign-in for `contactSupplier`; **guest contact behavior on live DEV has not been tested**. Do not turn this source-code observation into runtime FAIL.

## Verification matrix
| Capability | Observation | QA conclusion |
|---|---|---|
| Home render + visible public content | Actually observed in browser tab | VISUAL CONTENT OBSERVED (not full UX PASS) |
| Search navigation/filtering/results | Linked UI visible, no action executed | NOT TESTED |
| Supplier/program detail | Link targets visible, no navigation executed | NOT TESTED |
| Supplier ongoing-program fields | User screenshot of DEV + ZIP implementation | USER-SUPPLIED VISUAL EVIDENCE / CODE-PRESENT; persistence not tested |
| Guest → WhatsApp/phone Lead | Browser session authenticated; ZIP blocks guests | DEV RUNTIME NOT TESTED; P0 decision required |
| Signup, role switch, verified, reviews, admin | No flows submitted/visited | NOT TESTED |
| Legal | Footer links visible | CONTENT/CONSENT VERSION NOT TESTED |
| Mobile 390×844, 768, 1280 | No viewport-controlled DEV browser session | ENVIRONMENT BLOCKED / NOT TESTED |
| Production, real supplier threshold | Not accessed | NOT TESTED |

**Tooling limitation:** Connected Browser integration provides **read-only context of open tabs** in Chat mode, not navigation or interaction. Independent local Chromium is installed, but the local runtime cannot resolve the DEV hostname over DNS (`NameResolutionError`). The public web fetch for the site also failed. These are **environment/access limitations, not application failures**.

## Product/Release consequences
1. Update #3: the DEV homepage **has visible** discovery entry points, categories and program cards; do **not** mark search flow PASS without navigation/results test.
2. Keep #6 guest contact and #5/#8 multi-role as *code-vs-scope decision items*, not claimed DEV runtime failures.
3. #17/#11 need a live browser session with network/interaction access, authenticated + guest states and viewport control before E2E/Responsive PASS.
4. #9: sample/QA supply shown in DEV does **not** establish real supplier launch coverage.
5. Do not change Scope Lock, close Issues or approve launch on the basis of a single-page browser observation.

**Next action:** Run a controlled, read-only browser QA in a network-enabled environment, starting with guest search → supplier/program detail → contact gate visible behavior (no actual lead submission), followed by a controlled test-account session only with explicit data-write approval.
