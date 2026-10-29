# Dog License Page — Prototype Review Notes

## Typography — verified from Figma reference (node 2:149, file akOalEOGS00nzFc8NFOF5u)

These values were confirmed from the reference frame inspection. Previously-proposed values
have been replaced with verified reference values.

| Element | Family | Weight | Size (desktop) | Line-height |
|---|---|---|---|---|
| H1 (hero) | Montserrat | 800 (ExtraBold) | clamp(40px, 5.5vw, 67px) | 1.05 |
| Hero subtitle | Lora | Italic 400 | 25px | 1.32 |
| H2 (content sections) | Montserrat | 800 (ExtraBold) | clamp(28px, 4vw, 45px) | 1.2 |
| H2 (hero subsection "Who can apply") | Montserrat | 800 (ExtraBold) | clamp(22px, 3vw, 30px) | 1.3 |
| Body | Lora | 400 | 18px | 2.167 (~39px) |
| Fact sidebar label | Montserrat | 500 (Medium) | 13px | 1.4 |
| Fact sidebar value | Lora | 400 | 15px | 1.6 |
| TOC heading | Montserrat | 800 (ExtraBold) | 13px (uppercase) | — |
| TOC link | Montserrat | 700 (Bold) | 14px | 1.4 |
| Breadcrumb | Montserrat | 600 (SemiBold) | 13px (uppercase) | — |

Google Fonts load (added weight 500 and 800 for Montserrat):
`family=Montserrat:wght@400;500;600;700;800`


## Color tokens — verified from reference frame

| Token | Hex | Use |
|---|---|---|
| `--brand/charles-river-blue` | `#091f2f` | Headings, TOC circles, nav labels, page navy |
| `--brand/optimistic-blue` | `#1871bd` | Links, active TOC circle, TOC link hover |
| `--brand/freedom-trail-red` | `#d22d23` | Breadcrumb current page indicator |
| `--alias/body-text` | `#58585b` | Body paragraphs, sidebar values, descriptions |
| `--alias/mid-grey` | `#d2d2d2` | Section dividers, fact sidebar row borders, TOC connector lines |
| `--alias/off-white` | `#f2f2f2` | Content zone background |
| Accordion trigger bg | `#ededed` | `--!-cob/color/neutral/50` (verified, prev session) |


## Page layout — implemented from reference frame (2:149)

### Zone structure (three zones stacked)

**Hero zone (white background):**
- Two-column grid: `1fr 301px`, 64px gap
- Left: H1 + italic subtitle (25px Lora) + wavy SVG divider + body text + "Who can apply" subsection
- Right: compact fact sidebar with dashed-border rows (contact, fees, deadline, method)
- Breadcrumb above the grid (uppercase Montserrat, blue links, red current page)
- Mobile: stacks to single column; fact sidebar rows remain below content

**Content zone (off-white `#f2f2f2` background):**
- Two-column grid: `280px 1fr`, 40px gap
- Left: sticky "On this page" TOC — numbered circles (filled blue = active, outlined navy = inactive) connected by dashed vertical lines
- Right: sections separated by the official CoB wavy SVG divider
- Mobile: TOC becomes a horizontal chip grid above sections
- Desktop: TOC sticks at `top: 24px` as user scrolls

**Related resources (dark navy `#091f2f` background):**
- Three items in a vertical list; each item has a title column (300px, Lora Italic 20px, blue) and a body column (description + department label)
- Dashed right border on title column, row borders between items
- Mobile: title and body stack vertically

### Section structure (5 sections, reduced from 7)

Previous 7 sections → 5 sections:

| Old | New |
|---|---|
| #first-or-renewal | Content merged into #before-you-apply (renewal note as callout) |
| #before-you-apply | #before-you-apply (expanded — now includes merged renewal guidance + required docs checklist) |
| #fees-deadlines | #fees (renamed) |
| #how-to-apply | #how-to-apply (preserved, accordions unchanged) |
| #after-you-apply | #after-you-apply (preserved) |
| #update-replace | Removed — content moved into #get-help as a closing note |
| #get-help | #get-help (preserved, now includes update/replace contact guidance) |

All TOC labels and anchor links updated to match the new section IDs.


## Logo — updated implementation (2026-10-15)

**Previous:** CSS/HTML text approximation using verified colors (`#091f2f`, `#fb4d42`).

**Current:** PNG screenshot of CoB design system header component (Figma file `fEQ6ockidCAIh10p1hsqkC`, node `5726:3237` "Header 1280px+") saved as `assets/header-nav.png` (1291×113px).

CSS crop shows only the main nav row (logo + tagline area):
- `.cob-logo { overflow: hidden; width: 370px; height: 73px; }`
- `.cob-logo__img { width: 1291px; height: 113px; margin-top: -40px; }`

The `margin-top: -40px` hides the trustbar portion of the combined screenshot, exposing
the "CITY of BOSTON · Mayor Michelle Wu" wordmark. The container clips to 370px width to
exclude navigation links from the right side of the image.

**Still needed for production:** Standalone SVG export of the CoB primary logo from the
Figma brand assets page (file `fEQ6ockidCAIh10p1hsqkC`, node `5032:2619`). The PNG is an
approximation from a component screenshot and should be replaced with the official SVG
export before publishing.

**Footer logo:** "B" + red bar CSS approximation is still in place. Same replacement
recommended from the brand assets node above.

**Asset expiry note:** Figma MCP asset URLs (`figma.com/api/mcp/asset/...`) are temporary
(expire after 7 days). Both images were saved locally to `assets/` and are no longer
dependent on the Figma URL.


## Section divider — official CoB pattern

SVG file `assets/divider.svg` (15.3 KB) downloaded from the reference Figma frame
(node `2:149`, image node `imgFrame2`). This is the authentic CoB wave/zigzag repeating
pattern used between sections on the live site. Dimensions: 1531.2 × 8.7998px, fill `#E0E0E0`.

Applied as a CSS background image on `hr.section-divider` with `background-size: 1531px 9px;
background-repeat: repeat-x`.


## Accordion — verified implementation (unchanged from previous session)

Component: Figma node 4469:1783, variant Bordered=True / Single Select=False.

| Token | Value | Use |
|---|---|---|
| `--!-cob/color/neutral/50` | `#ededed` | Trigger button background |
| `--!-cob/space/100` | `8px` | Gap between accordion items |
| `--!-cob/space/200` | `16px` | Trigger + panel padding (vertical) |
| `--!-cob/space/250` | `20px` | Trigger + panel padding (horizontal) |
| `--!-cob/radius/md` | `4px` | Trigger and item border-radius |
| `--!-cob/font-size/ui/xl` | `20px` | Trigger heading font-size |
| `--!-cob/font-lineheight/ui/xl` | `28px` | Trigger heading line-height |
| `--!-cob/font-letterspacing/ui/xl` | `0.0173px` | Trigger heading letter-spacing |

Accordion implementation is unchanged. Three items (Apply online, Apply by mail, Apply in person),
all start collapsed, Expand/Collapse all controls, Process Lists inside, age-70+ notice above,
no-JS fallback, print CSS, anchor-opens-panel JS.


## Design choices requiring team confirmation

### Primary button (filled blue)
The CoB Button instance inspected (node 5544:13737) was the secondary/outlined variant.
The "Apply online" button uses a filled `#1871bd` background — proposed, not directly
verified from Figma. Confirm against a CoB Button component frame before publishing.

### TOC scroll-based highlight
The TOC uses `IntersectionObserver` with `rootMargin: '-5% 0px -70% 0px'` to highlight the
active section circle as the user scrolls. Falls back to first item active if JS is unavailable
or `IntersectionObserver` is unsupported. Verify the threshold works correctly across section
heights.

### "Renewing" guidance
The renewal process is described with a callout note pointing users to look up their license
number, but does NOT assert that the first-license and renewal processes are otherwise identical.
See policy question 1 below.

### Footer utility link paths
Footer links (Privacy Policy, etc.) use plausible boston.gov paths that were not verified
against the live site. Check before publishing.


## Policy questions for Animal Care and Control

These items cannot be resolved from published page content. Do not add content to the
resident-facing page until the answers are confirmed.

1. **First license vs. renewal process** — Is there any procedural difference beyond
   providing the existing license number? The current page treats them the same except for
   the license number requirement. Confirm before asserting they are identical.

2. **In-person visit requirements** — The existing page previously stated "appointment only
   until February 6, 2026." That date is past. What is the current policy?
   **Staff action required:** Verify and update the prototype in-person section.

3. **Mail processing time** — How long should applicants expect to wait? Especially relevant
   for residents applying close to the April 1 deadline.

4. **Grace period after April 1** — Is there any grace period before the $50 fine is issued?

5. **Age-70+ waiver documentation** — What identification must a resident present to use the
   fee waiver by mail or in person?

6. **Update or replace a license** — What steps and fees apply for a lost tag, address
   change, or ownership change? (The "Update or replace" section was removed from the
   prototype; contact guidance remains in Get help.)


## Outdated notice — staff review required

The live boston.gov dog-license page contained:
> "Appointment only until February 6, 2026" (animal shelter in-person visits)

That date is past (current date: 2026-10-15). The prototype omits this notice and directs
residents to contact the office to confirm visit requirements. The live page should be
updated to remove or replace this notice.


## Checks completed on the prototype (2026-10-15 redesign)

- **No duplicate HTML IDs** — verified programmatically.
- **TOC anchors** — all five (`#before-you-apply`, `#fees`, `#how-to-apply`, `#after-you-apply`,
  `#get-help`) resolve to existing `h2` elements. TOC count matches section count.
- **Accordion JS** — preserved unchanged: `openFromHash()`, `setPanel()`, expand/collapse all.
  Hash links `#apply-online`, `#apply-by-mail`, `#apply-in-person` open the respective panels.
- **Noscript fallback** — `<noscript>` CSS shows all accordion panels when JS is disabled.
- **Print CSS** — accordion panels forced open, controls hidden.
- **Logo asset** — downloaded locally to `assets/header-nav.png` (no expired URL dependency).
- **Section divider** — downloaded locally to `assets/divider.svg`.
- **Fee waiver notice** — age-70+ restriction preserved above accordion group AND inside the
  online application accordion panel step 2.
- **No template leftovers** — zoning approvals, approved site plans, approval stages, dummy
  renewal steps not present.
- **Verified links** — all `href` values use confirmed boston.gov or cityofboston.gov URLs.

Not checked (requires browser/device testing):
- Actual logo crop alignment (depends on precise trustbar height in rendered PNG)
- Screen reader announcement order
- Color contrast ratios (WCAG 2.1 AA)
- High-contrast mode
- Scroll-based TOC highlight threshold accuracy


## Components still needing Figma verification for production

| Gap | Current treatment in prototype |
|---|---|
| Primary button (filled) | `#1871bd` fill, 12px radius — proposed |
| Header logo | PNG crop from component screenshot — needs standalone SVG |
| Footer B logo | CSS approximation — needs official SVG |
| Callout / notice component | CSS approximation (`#f6f6f6` + grey left border) |
| Fee table component | Semantic `<table>` with verified CoB neutral colors |
| TOC scroll threshold | `IntersectionObserver` at `-5%/−70%` — tune per tested section heights |
| Footer utility links | Plausible paths — not verified against live site |
