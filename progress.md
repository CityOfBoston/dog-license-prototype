# V3 Figma Review — Progress

## Last updated: 2026-10-27

---

## What was completed

All V3 screens read from Figma via MCP. No project files were edited, no prototype changed.

- Read metadata for node `345:12988` ("new / renewal"), parsed 281 KB XML.
- Drilled into all 27 top-level children and all key descendant frames.
- Extracted text content, form fields, fee tables, step labels.
- Took and downloaded screenshots for all key screens:

| File | Node | Description |
|---|---|---|
| `canvas-overview.png` | 345:12988 | Full canvas thumbnail (800×370) |
| `concept2-info-page.png` | 345:12989 | Info page — 800×4800, too tall to read inline |
| `intro-screen.png` | 345:13906 | Application intro/landing screen |
| `step1-owner-info.png` | 345:14015 | Step 1 — Owner information |
| `step2-21-dogs.png` | 345:14141 | Step 2.21 — Dogs (1 of 3) |
| `step2-22-dogs.png` | 345:14374 | Step 2.22 — Dogs (2 of 3) |
| `step3-review.png` | 345:13747 | Step 3 — Review your application |
| `lookup-screen7.png` | 345:14706 | Dog License Lookup — search by license number |
| `lookup-screen8.png` | 345:14828 | Dog License Lookup — search by owner name |
| `leaving-modals.png` | 345:15073 | Two "leaving workflow" modal dialogs |

---

## Figma reference

- **File:** Dog-License — **File key:** `akOalEOGS00nzFc8NFOF5u`
- **Root node:** `345:12988` ("new / renewal")
- **Figma URL:** https://www.figma.com/design/akOalEOGS00nzFc8NFOF5u/Dog-License?node-id=345-12988

---

## Complete screen-by-screen findings (confirmed from screenshots)

---

### 0 · Intro screen / Application landing (345:13906)

**Breadcrumb:** Home > Animal Care and Control > License your dog > Dog License Application

**Title:** Dog License Application

**Body:** "Boston requires all dog owners to license their dogs each year. A license helps Animal Control support rabies prevention, protect public health, and identify your pet."

**Before you start** (bullets):
- Your dog must have proof of rabies vaccination.
- Puppies must be licensed when they reach six months of age.
- You must live in Boston to license your dog through the City of Boston.
- You may be subject to a fine if your dog is not licensed.

**What you'll need** (bullets):
- Rabies vaccination certificate — A photo or PDF of your dog's current rabies vaccination certificate from your veterinarian.
- Credit or debit card — Visa, Mastercard, American Express, or Discover. A 2.75% service charge applies, with a $1 minimum.

**License Period:** Dog licenses are valid from April 1 through March 31 each year.

**License Fees** (table — 3 columns: Dog type | Sex | Annual license fee):
| Dog type | Sex | Annual license fee |
|---|---|---|
| Spayed or neutered dog | Female or male | $15 |
| Unspayed or unneutered dog | Female or male | $30 |

Note below table: "Online payments have a 2.75% service charge, with a $1 minimum. Accepted cards: American Express, Discover, Mastercard, and Visa."

**CTA:** "Start your application online" (blue button, full-width)
**Secondary link:** "Or apply in person or by mail"
**Questions:** "Questions? Email Animal Care and Control at xxx@boston.gov." ⚠️ placeholder email

---

### 1 · Step 1 — Owner information (345:14015)

**Breadcrumb:** Home > Animal Care and Control > License your dog > Dog License Application ✓

**Left stepper (NYS Stepper — 5 steps):**
1. Start application ← active (filled circle)
2. Owner information
3. Dog information
4. Review application
5. Payment?

⚠️ Stepper label at top: `{labelText}` — placeholder not replaced.
⚠️ The active step is shown as "Start application" but the page title is "Owner information" — label/step numbering mismatch; needs clarification.

**Title:** Owner information
**Subtitle:** "Review your contact information and make any necessary updates."

**Before you continue** (section heading + bullets):
- You must be at least 18 years old.
- You must provide proof of your dog's current rabies vaccination.
- You must provide proof that your dog has been spayed or neutered, if applicable.
- You must pay any outstanding violations before your application can be completed.
- If the required certificates are not already on file, you must provide them during the application process. Missing documentation may delay or prevent approval.

**Your contact information** (section):
- Owners full name \*
- Phone number \* (masked format: ( ) ___-____)
- Email address \*

**Your Boston address** (section):
- Street address \*
- Apartment or unit number \*
- Neighborhood \* (dropdown: "- Select -")
- Zipcode \*

**Buttons:** Back | Continue

---

### 2.21 · Step 2.21 — Dogs in this application — 1 of 3 (345:14141)

**Breadcrumb:** Home > Departments > Registry: Birth, Death, and Marriage and Marriage Intention > Birth Certificates ⚠️ WRONG — template placeholder not replaced.

**Left stepper (CoB Stepper — 4 steps):** ⚠️ Different component from Step 1's NYS Stepper.
- Header label: "Request a Dog License" ✓
- 1 Owner information ✓ (checkmark — complete)
- 2 Dog information ← active
- 3 Review
- 4 Payment

**Counter:** "1 of 3 dogs added"
**Title:** Dogs in this application
**Subtitle:** "Complete details and documents for each dog. You can include new licenses and renewals in the same application."

**First Dog** (badge: "Details needed" — orange):
- `Complete Details` accordion (expanded)

*Dog's details:*
- Dog's name \*
- Age (years) \*, Age(months) \*
- Primary color \* (select), Secondary color (select)
- Primary breed \*, Secondary breed

*Sex and Spay Status \** (4 radio tiles, inline pricing):
- Male — $30
- Neutered male — $15
- Neutered male — $15 ⚠️ DUPLICATE LABEL (should probably be "Spayed female" or "Intact female")
- Spayed female — $15

*Rabies vaccination:*
- "Your dog must have current rabies vaccination documentation. Enter the dates shown on the certificate."
- Vaccination date \* (date picker)
- Expiration date \* (date picker)
- Rabies vaccination certificate \* (file upload) — note: "For renewals, upload a new or updated certificate if needed. Accepted file size: up to 5 MB. Confirm supported file types with the development team." ⚠️ note still says "Confirm supported file types with the development team" — not final copy.

*Spay/neuter certificate* (Optional):
- "Upload proof if required and not already on file. Maximum file size: 5 MB."
- Choose files / drag here

*Additional comments* (Optional):
- `{inputText}` textarea placeholder

- "Remove" link (removes this dog)
- "Add another dog" link (bottom right)

⚠️ No "What are you applying for?" question on the first dog. The question appears only from the second dog onwards (see 2.22). If the first dog always enters through the Lookup flow (renewal), this may be intentional — but it needs confirmation.

**Buttons:** Back | Continue

---

### 2.22 · Step 2.22 — Dogs in this application — 2 of 3 (345:14374)

**Breadcrumb:** Same wrong placeholder as 2.21. ⚠️

**Counter:** "2 of 3 dogs added"
**Left stepper (CoB Stepper):** Same 4-step structure.

**Rio section** (badge: "Complete" — green):
- Collapsed / summary row. "Edit details" button.

**Second Dog section** (badge: "Details needed" — orange):
- "Complete Details" accordion (expanded)

*NEW question at top of second dog (absent from first dog):*
**What are you applying for? \***
- New License
- Renewal

Then same Dog's details, Sex/Spay Status, Rabies vaccination, Spay/neuter certificate, Additional comments as above.

- "Done with this dog" button (ends editing this dog and collapses it to a summary) — different from the first dog which uses Continue.
- "Remove" link
- "Add another dog" link

**Buttons:** Back | Continue

---

### 3 · Step 3 — Review your application (345:13747)

**Breadcrumb:** Home > Departments > Registry: Birth, Death, and Marriage and Marriage Intention > Birth Certificates ⚠️ WRONG placeholder.

**Left stepper (NYS Stepper — 5 steps):** Reverts to NYS Stepper (same as Step 1).
- `{labelText}` ⚠️ still unset
- 1 Start application
- 2 Owner information
- 3 Dog information
- 4 Review application ← active
- 5 Payment?

**Title:** Review your application
**Subtitle:** "Review your information and uploaded documents before continuing to payment. You can edit any section if something needs to change."

**Owners information** (section + Edit link):
- Application type: Renewal
- Owner Name: American Bulldog ⚠️ placeholder (dog breed, not a name)
- Phone number: Male, neutered ⚠️ placeholder
- Email: 6 ⚠️ placeholder
- Address: 52R River Street, Unit 2 / Gray and white ⚠️ placeholder

**Dog 1 — Rio** (section + Edit link):
- Application type: Renewal
- Breed: American Bulldog
- Sex: Male, neutered
- Age: 6
- Spayed or neutered: Yes
- Coat Color: Gray and white
- Uploaded documents:
  - Rabies vaccination certificate — "Uploaded successfully" ✓
  - Rabies vaccination certificate — "Uploaded successfully" ✓ ⚠️ Two identical documents listed — intentional (vaccination + spay cert both named "Rabies vaccination certificate"?), or labeling error.

**Dog 2 — Peter** (section + Edit link):
- Same breed/details as Rio (identical placeholder data)
- Uploaded documents: same two "Rabies vaccination certificate — Uploaded successfully" ⚠️ same labeling issue

**License fees:**
- Rio — $15.00 (Neutered male)
- ⚠️ Peter has NO fee line item. Either Peter is $0 (free — but no 70+ waiver scenario shown), or this is a design oversight.
- **Total: 15.00**
- Note: "An online service charge of 2.75% (minimum $1.00) applies. Invoice Cloud will show the amount due before payment."

**Buttons:** Back | Continue to payment
**Below buttons:** "You'll continue to Invoice Cloud to pay for your dog licenses."

---

### 4 · Dog License Lookup — Search by license number (345:14706)

**Breadcrumb:** Home > Animal Care and Control > License your dog > Find your dog's license ✓

**Title:** Find your dog's license
**Subtitle:** "Find your dog's license to view details, check its status, or renew."

**How would you like to find your license? \*** (radio tiles):
- ● I know my license number (selected — blue highlight)
- ○ I want to search by owner name

*When "I know my license number" is selected:*
- License tag number \* — "You can find your license number on your dog's tag or previous license records."
- License year \*
- Dog's name \*
- **Search** button (full-width blue)

**Need help finding your license?**
"If you don't remember your license number or can't provide the details needed to search, call Animal Care and Control for help."
- 617-635-5348
- Monday–Friday, 8 a.m.–4 p.m.
- Email: animalcontrol@boston.gov

---

### 4b · Dog License Lookup — Search by owner name (345:14828)

Same header/breadcrumb/title as Screen 7.

*When "I want to search by owner name" is selected:*
- Owner's first name \*
- Owner's last name \*
- License year \*
- Dog's name \*
- **Search** button

Same help section below.

---

### 5 · Leaving the workflow — two modals (345:15073)

**Modal 1 — "Leave the dog license application?"**
Body: "You haven't submitted your application. Leaving now may cause you to lose the information you've entered."
- Primary: **Stay in application** (blue)
- Secondary: **Leave application** (outline)

**Modal 2 — "Continue to payment?"**
Body: "You'll leave this application and go to Invoice Cloud to pay for your dog licenses. Review the total, including the service charge, before paying."
- Primary: **Continue to Invoice Cloud** (blue)
- Secondary: **Back to review** (outline)

---

## Confirmed fees (from both intro screen and Step 3)

| Dog type | Fee |
|---|---|
| Spayed or neutered dog | $15/year |
| Unspayed/unneutered dog | $30/year |
| Owner 70+ (mail/in-person only) | No fee — not shown in intro screen table; only in Concept 2 info page |
| Online service charge | 2.75%, minimum $1.00 |
| Accepted cards | AmEx, Discover, Mastercard, Visa |

---

## Concept 2 info page (345:12989) — from metadata only (screenshot too tall to read inline)

Long-form service page with 9 sections; see previous session notes. Section content confirmed from metadata extraction. Cannot confirm visual styling from screenshot (800×4800 px exceeds Read tool limit). Open `references/v3-images/concept2-info-page.png` locally to review.

---

## Flags and ambiguities — consolidated

### Content / copy
| # | Location | Issue |
|---|---|---|
| 1 | Intro screen | Questions email is `xxx@boston.gov` — placeholder |
| 2 | Step 1 stepper | Top label `{labelText}` — token not replaced |
| 3 | Step 1 stepper | Active step shown as "Start application" but page title is "Owner information" — step label/position mismatch |
| 4 | Steps 2.21, 2.22, 3 | Breadcrumb shows "Registry: Birth, Death, and Marriage…" — wrong template breadcrumb |
| 5 | Step 2.21 | Rabies cert upload note ends with "Confirm supported file types with the development team." — unfinished dev note left in |
| 6 | Step 2.21 | Sex/Spay Status has two identical "Neutered male — $15" options. Third option should probably be "Intact female — $30" |
| 7 | Step 3 review | All owner/dog placeholder data is wrong (breed used as name, etc.) — expected for prototype, but flag for future review |
| 8 | Step 3 review | Two uploaded documents both labeled "Rabies vaccination certificate" — may intend to show rabies cert + spay cert, but spay cert label is wrong |
| 9 | Step 3 fees | Peter has no fee line item in the summary — appears incomplete |
| 10 | Concept 2 "Fees" | One table says "2.7% service fee"; everywhere else says "2.75%" — likely typo |
| 11 | Concept 2 "How to apply" | Accordion List is empty — no options (Online / By mail / In person) filled in |

### Design / component
| # | Location | Issue |
|---|---|---|
| 12 | Steps 1 & 3 vs. 2.21 & 2.22 | NYS Stepper (5 steps) vs. CoB Stepper (4 steps) — different components, different step counts, no "Start application" in CoB version |
| 13 | Step 2 (first dog) | No "What are you applying for?" question; step 2.22 (second dog onwards) adds it — may be intentional (first dog always from Lookup/renewal) but unconfirmed |
| 14 | Four "Step 1 - Desktop" variants | At x=3463–6458 — role vs. main Step 1 at x=8331 is unclear; may be archived |
| 15 | Intro screen | 70+ fee waiver not shown in the intro fees table; only in Concept 2 — inconsistency |

---

## Unfinished work

- [ ] Read Concept 2 info page visually (file is too tall for inline read — open locally)
- [ ] Confirm the role of the four "Step 1 - Desktop" variants (archived vs. live alternate states)
- [ ] Clarify stepper inconsistency (NYS vs. CoB Stepper, 5-step vs. 4-step)
- [ ] Confirm whether first dog skipping "What are you applying for?" is intentional
- [ ] Confirm whether Peter's missing fee is intentional or incomplete
- [ ] Confirm whether the Accordion List in "How to apply" will be populated
- [ ] Get actual email address to replace `xxx@boston.gov` placeholder

---

---

## V3 Implementation — completed 2026-10-27

### Files changed

| File | What changed |
|---|---|
| `application-prototype/index.html` | 9 targeted edits to the JS section only. HTML structure, CSS, and layout unchanged. |

### Changes made

1. **Consistent 4-step stepper** — Already correct (Owner information → Dog information → Review → Payment). Breadcrumbs were already correct in code; the wrong breadcrumbs existed only in the Figma design prototype.

2. **Sex/Spay options fixed** — `SEX_MAP` and all `sexOpt()` calls updated:
   - Old: Male $30, Neutered male $15, Female $30, Spayed female $15
   - New: **Intact male** $30, Neutered male $15, **Intact female** $30, Spayed female $15
   - `fee()` logic unchanged (neutral/spayed → $15, else → $30).
   - `LOOKUP_RECORDS` Buddy's sex updated from `'male'` → `'intact-male'`.

3. **Application type on ALL dogs** — `newDog()` now defaults `method:''` (unset). For manually entered dogs (all entries), the dog form shows "What are you applying for?" (New license / Renewal) at the top. For dogs pre-filled from the lookup (`fromLookup:true`), the form shows a blue info box: "Application type: Renewal — carried forward from license lookup" with a prototype note.

4. **Method tag on dog cards** — Cards now show a parenthetical tag `(Renewal)` or `(New license)` next to the dog name once the method is selected. The old on-card method radios are removed.

5. **Validation updated** — "Done with this dog" and the "Continue" button now require name + application type + sex/status. Error message lists which specific fields are missing.

6. **`saveDogFields()`** — Now saves the method radio selection in addition to other fields.

7. **`buildReview()` updated**:
   - Application type shows "New license" (was "New dog").
   - Lookup dogs show "Prefilled from license lookup (simulated)." note in the review.
   - Each dog now shows Age in the review.
   - Documents section shows both rabies cert and spay/neuter cert if uploaded, each with its actual filename.
   - Fee line shown for **every dog** — total recalculates from all dogs' selected sex/status.

8. **`startRenewal()`** — Dogs from lookup now receive `fromLookup:true`.

### What was tested (manually, by opening the file)

- **New license entry**: Start application → owner form → Step 2 dog form shows "What are you applying for?" → select "New license" → fill name + sex → Done → card shows "(New license)" tag → Continue to Review → application type shows "New license", fee line present.
- **Renewal entry (manual)**: Same as above but select "Renewal" in the dog form.
- **Renewal entry (via lookup)**: Find license → select dog(s) → Renew → owner pre-filled → Step 2 dog form shows "Application type: Renewal — carried forward" (no radio) → fill name (already filled) + sex (already filled) → Done works → Review shows "Renewal (Prefilled from license lookup)".
- **Multiple dogs**: Add second dog → each has independent method question → Review shows separate fee line for each dog, total sums correctly.
- **Edit dog from review**: Edit button → returns to Step 2 with dog form open → change sex → Done → Continue → Review recalculates fees and total.
- **Both leaving dialogs**: Back on Step 1 with data → "Leave the dog license application?" modal. Continue to payment → "Continue to payment?" modal. Both secondary actions (Stay / Back to review) dismiss correctly.
- **Data preservation**: Navigating Back from dogs → owner fields preserved. Navigating Back from payment → review rebuilt correctly.

### Remaining open questions (not invented, documented)

1. **"How to apply" accordion** in the Concept 2 info page (`index.html`) — accordion currently shows three placeholder items. No confirmed content for the three options. Outstanding content gap.
2. **Correct email address** — intro screen shows `animalcontrol@boston.gov` (already in code). The Figma had `xxx@boston.gov` as placeholder; the prototype already has the real address.
3. **Accepted file types** — dog form note says "Confirm supported file types with the development team." — not resolved.
4. **Post-payment behavior** — Invoice Cloud return URL, confirmation screen, failed-payment handling — not confirmed. Documented on the payment screen as an open question.
5. **70+ fee waiver** — not shown in the application flow (only in the info page). The application has no age-of-owner field or waiver pathway. Policy confirmation and UX design needed before implementing.
6. **Backend lookup behavior** — the renewal lookup is fully simulated (any search returns the 3 hardcoded records). Actual API contract, error states, and no-results handling are not designed.

### How to open the prototype on Windows

Double-click `application-prototype\index.html`, or run in PowerShell:

```powershell
Start-Process "C:\Users\40085676\dog-license-page\application-prototype\index.html"
```

The information page is at the parent directory:

```powershell
Start-Process "C:\Users\40085676\dog-license-page\index.html"
```

Both files are self-contained and open directly in any browser without a local server.

---

---

## Session 2026-10-28 — Lookup results redesign

### Changes made

1. **Replaced multi-dog lookup results with single-dog review page** — `view-lookup-results` now matches Figma Step 0.2 - Desktop RN (node `345:13628`):
   - Title: "Review your dog information"
   - Subhead: "We found an existing license. Review the information below..."
   - Yellow rabies warning banner (shown if `rabiesExpired:true` on the record)
   - Single dog card (`review-block`) with: dog name + license number + two status badges (license / rabies cert), then three labeled sections: Dog details · License details · Rabies vaccination
   - Two buttons: "Search another dog" (back, left) | "Renew your license" (blue, right)
   - "Something look wrong?" help section with phone and email

2. **Results page isolated from renewal path** — `doSearch()` now calls `setMode('landing')` (full-width, no stepper). The stepper only activates when the user explicitly clicks "Renew your license," which calls `setPath('renewal')` then `startRenewal()` (enters at Step 1 — Owner information, with Step 0 marked complete).

3. **Dog name matching in search** — entering a dog name (e.g. "Luna", "Milo") in the search form returns that record. Empty search or no match falls back to Buddy.

### New JS functions

| Function | Purpose |
|---|---|
| `renderSingleResult(r)` | Populates `#result-detail-card` from a single LOOKUP_RECORDS entry |
| `dlRow(label, value)` | Returns a `detail-dl__row` dt/dd pair |

### State changes

- `var currentResult = null` — tracks the single found record
- `doSearch()` sets `currentResult`, calls `renderSingleResult`, then `setMode('landing')`
- `btn-renew` handler sets `lookupSelected`, calls `setPath('renewal')`, then `startRenewal()`

### Removed

- `renderResults()`, `toggleSelect()`, `updateSelectBar()` — multi-select card functions deleted (multi-dog selection UI removed)
- Old HTML: `#result-cards-wrap`, `#results-summary`, `.select-bar`, `#select-bar-info` (all removed from `view-lookup-results`)
