# Accessibility compliance notes

## 1. Project
- Project: CBC Tutor and Practice (labeled Human Physiology, no course code)
- Files covered: cbc-tutor.html (single file, images embedded). Print companions: CBC-case-walkthrough-worksheet.pdf and CBC-case-answer-key.pdf.
- Date: November 17, 2026 (sixth revision: the sentence under each intro headline changed from light grey to dark navy)

## 2. WCAG version and level
Target: WCAG 2.2 AA, AAA contrast where achievable.

| Criterion | Status |
|---|---|
| 1.1.1 Non-text content | Met. Seven micrographs have descriptive alt text. Repeated thumbnails are decorative (empty alt). The shift graph has a text label that reads out every bar value. |
| 1.3.1 Info and relationships | Met. Landmarks, ordered headings, tables with th scope, fieldset and legend on every question, including the walk-through questions. Concept maps are nested lists. Formula dropdowns have spoken names. |
| 1.4.1 Use of color | Met. Flags, verdicts, completed cases and calculation status carry text. |
| 1.4.3 / 1.4.6 Contrast | AAA for all text. See section 3. |
| 1.4.10 Reflow | Met. Grids collapse to one column, formula rows wrap, concept maps become an indented outline below 820px, wide tables scroll inside a focusable region. |
| 1.4.13 Content on hover or focus | Met. Term definitions open on click or Enter and close with Escape. |
| 2.1.1 Keyboard | Met. See section 4. |
| 2.2.2 Pause, stop, hide | Met. The intro advances every 7 seconds and stops at the menu. Pause, Back, Continue and Skip intro are always available. No autoplay with reduced motion turned on. |
| 2.3.3 Motion | Met. prefers-reduced-motion removes all animation and transitions. |
| 2.4.1 Bypass blocks | Met. Skip link to main. |
| 2.4.7 / 2.4.11 Focus visible | Met. 3px outline on every interactive element. |
| 2.5.8 Target size | Met. Controls are 40 to 44px or larger. |
| 3.3.1 / 3.3.3 Error identification and suggestion | Met. Wrong formula setups name the box to recheck, wrong answers say how to round, wrong walk-through answers point back to the reference range. Show the formula and Show the answer keep students from being blocked on the math. |
| 3.3.2 Labels | Met. Every input has a label or an accessible name. |
| 4.1.2 Name, role, value | Met. Tabs use tablist/tab/tabpanel; terms use aria-expanded; the case list is a native details element. |
| 4.1.3 Status messages | Met. Results, feedback, calculator output and interpreter output are in aria-live regions. |

## 3. Color contrast audit (calculated)

| Text | Background | Ratio | Result |
|---|---|---|---|
| Ink #060B1A | White #FFFFFF | 19.62 | AAA |
| Ink #060B1A | Page #FAFAF9 | 18.78 | AAA |
| Ink #060B1A | Tint #EDF1F3 | 17.26 | AAA |
| Maroon #7A1F2B | White #FFFFFF | 10.20 | AAA |
| Maroon #7A1F2B | Page #FAFAF9 | 9.77 | AAA |
| Muted #414B5A | White #FFFFFF | 8.83 | AAA |
| Muted #414B5A | Tint #EDF1F3 | 7.77 | AAA |
| Intro text #1A2233 | White #FFFFFF | 15.90 | AAA |
| Intro text #1A2233 | Intro background #F1F4F8 | 14.42 | AAA |
| White #FFFFFF | Ink #060B1A | 19.62 | AAA |
| White #FFFFFF | Maroon #7A1F2B (High flag) | 10.20 | AAA |
| Control borders #6B7483 | White #FFFFFF | 4.72 | Passes 3:1 for controls and graphics |

## 4. Keyboard navigation flow (checked in code, not yet by hand)
Home: Skip intro, Back, Pause or Play, Continue, then the Learn, Practice and Quiz cards. Inside a section: Home button, the four tabs, then the panel. In a case: Give me a random case, the case list, the calculator, the four calculations, Check my flags, the five walk-through questions in order, then the pattern question. Focus moves to each new step heading as it opens.

## 5. Testing done
- Data check on all 60 cases: differential adds to 100, every value's flag matches the intended pattern, exactly one correct answer out of four, no duplicate stories or numbers.
- Scripted full run (calculate, flag, walk-through, pattern) on 11 cases spread across every pattern, plus the calculation flow on the original ten.
- Visual check in headless Chrome at 1200px and 400px wide.
- Sixth revision: page loaded in headless Chrome with no script errors and no missing images, and every input had a label. The intro sentence measured at #1A2233, fully opaque.
- PDFs: page count and layout checked by rendering the pages; fonts embedded.
- Not yet done: a pass with VoiceOver or NVDA, a manual keyboard pass in a real browser, and a real test print.

## 6. Known limitations and remediation
- Fixed in the sixth revision: the sentence under each intro headline was showing in #E7EAF0 on white (about 1.2 to 1), a color left over from the earlier dark header. It now shows in #1A2233.
- The page has no internal links to other course pages, so there is nothing that needs target="_top". The two outside links (MedlinePlus and OpenStax) open in a new tab.
- The two PDFs are print documents. They are not tagged for screen readers. A student who needs an accessible version should get the questions in an accessible format.
- Cases 11 to 60 are built from ten pattern templates with five patients each. The numbers were generated to fit each pattern and then checked; they are teaching values, not real patients. Reference ranges are the non-pregnant adult ranges for every case, including the one pregnant patient.
- No photo of a band neutrophil. The OpenStax source has none.
- The five white cell photos are small in the source file and are shown at 132px so they stay sharp.
- Image license: OpenStax lists Anatomy and Physiology 2e as CC BY 4.0 on its site, while the source repository metadata says CC BY-NC-SA 4.0. The light micrographs carry a credit to the Regents of University of Michigan Medical School (2012). Confirm terms before using the page in a paid product.
- Left and right shift bars are illustrative examples, labeled as such.
- Progress saves in the browser only.
- Fonts load from Google Fonts. If blocked, the page falls back to system fonts.

## 7. Reviewer
Drafted by Claude. Awaiting review by Dr. Sharilyn Rennie.
