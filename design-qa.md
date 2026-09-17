# Design QA

- Source visual truth: `/var/folders/nd/rgv0xnnj307gldjrz406j18h0000gn/T/codex-clipboard-ad8b677a-aa9c-490b-986f-ff409481df06.png`
- Implementation: `/Users/ruianyun/Nutstore Files/瑞安云/11_摄像头/AI原型/index.html`
- Browser-rendered evidence: Codex in-app browser tab 6 at `http://localhost:8766/?v=2`
- Viewport: 1280 × 720 CSS px, device scale factor 1
- Source dimensions: 220 × 694 px
- Implementation capture dimensions: 1280 × 720 px; left navigation region 220 × 720 CSS px
- Density normalization: source and implementation were reviewed at 1× CSS scale; the source was used as the focused left-panel reference.
- State: project tree expanded, “首页” selected, right-side product prototype on its home screen.

## Full-view comparison evidence

The rendered page preserves the requested two-region composition: a narrow white 220 px project navigator on the left and the interactive product prototype centered on the right. The left panel matches the source hierarchy, density, selected-row treatment, pale search field, subtle separators, and teal right edge. The product prototype remains visually distinct and fully visible.

## Focused region comparison evidence

The left navigation was checked as the focused region because it is the supplied source of truth. Typography, 30 px row rhythm, indentation, disclosure controls, folder/page icons, selected-row blue, header spacing, and search placement were compared at readable scale. No additional focused region was required because the right-side prototype was not part of the supplied correction reference and was intentionally preserved.

## Required fidelity surfaces

- Fonts and typography: compact system sans-serif hierarchy matches the source; title and page labels remain legible without unintended wrapping.
- Spacing and layout rhythm: 220 px sidebar, 30 px rows, nested indentation, and full-height structure match the source proportions.
- Colors and visual tokens: white panel, cool-gray text/icons, pale-blue selection, and teal divider align with the reference.
- Image and icon quality: crisp vector folder, document, search, and disclosure icons; no raster scaling artifacts.
- Copy and content: project title and all supplied page names are represented in the same hierarchy.

## Interaction verification

- Clicking “目的地风险查询” opens the risk-query screen.
- Clicking “订阅会员” opens the profile screen and membership sheet.
- Product folders expand and collapse.
- Search filters page names and restores the tree when cleared.
- Narrow screens keep the existing full-screen mobile prototype behavior.

## Findings

No actionable P0, P1, or P2 differences remain.

## Comparison history

- Pass 1: fresh browser render matched the source panel proportions and hierarchy. No P0/P1/P2 fix iteration was required.

## Follow-up polish

- P3: generic folder/document icon strokes differ slightly from Axure’s native icon glyphs, but their size, weight, and function are visually equivalent.

final result: passed

## Incremental QA · external Markdown requirement source

- Added `需求说明.md` as the editable source for every Chinese prototype module annotation.
- The HTML fetches the Markdown with cache disabled, parses the seven fixed lines under each module key and overrides only recognized Chinese fields.
- Unknown keys, unknown fields and empty values are ignored; malformed or unavailable Markdown falls back to the embedded catalog.
- `file://` explicitly uses the embedded fallback because browsers normally block local-file fetches. The external source is active through the existing localhost preview.
- Requirement points are mounted after the load attempt, so their accessible names use the latest Markdown title.

final result: passed

## Incremental QA · remove inspector footer copy

- Removed the supplemental footer description from the requirement inspector.
- Removed its HTML element, CSS rule and both runtime text assignments so the copy cannot reappear when switching requirement points.
- The six structured requirement fields and close interaction remain unchanged.

final result: passed

## Incremental QA · Chinese-only prototype annotations

- Module requirement points are now generated only inside the Chinese prototype (`data-locale="zh"`).
- The English prototype retains all screens, content and primary interactions but no longer receives annotation points or requirement-panel triggers.
- The shared requirement catalog remains bilingual for maintainability; runtime exposure is restricted to the Chinese column.

final result: passed

## Incremental QA · remove flowchart descriptions

- Reference: `/var/folders/nd/rgv0xnnj307gldjrz406j18h0000gn/T/codex-clipboard-5b9d5e57-5f3b-4155-a21a-d3e0a9a76f0b.png`.
- Removed the explanatory sentence beneath the title from all three native flowchart documents: risk query, restore purchase and membership subscription.
- Flowchart headings, legends, diagrams, branches and supporting cards remain unchanged.

final result: passed

## Incremental QA · external requirement inspector

- Reference: `/var/folders/nd/rgv0xnnj307gldjrz406j18h0000gn/T/codex-clipboard-05251980-db7b-43f7-8d0e-092c793e5041.png`.
- Replaced the centered modal and dimmed backdrop with a dedicated right-side requirement inspector outside the bilingual prototype area.
- Selecting a module point keeps both phone prototypes visible and operable while showing module overview, data source, preconditions, result, display limit and sorting in the third layout column.
- Switching between English and Chinese points updates the same inspector without reopening an overlay; labels and copy follow the selected prototype locale.
- Active points expose `aria-expanded=true`, reference the inspector with `aria-controls`, and receive a distinct selected state.
- Closing the inspector restores focus to its originating point. Escape also closes the inspector, with no backdrop-click behavior because the panel is non-modal.
- Navigating to another prototype screen or document closes stale inspector content automatically.
- Verified open, locale switch and close states in the in-app browser at `?v=42#home`; the accessibility tree confirms the prototype and inspector coexist as sibling regions.

No actionable P0, P1, or P2 issues remain in the requested scope.

final result: passed

## Incremental QA · flowchart decision geometry and label clearance

- Reference: `/var/folders/nd/rgv0xnnj307gldjrz406j18h0000gn/T/codex-clipboard-fab3c2e8-f87b-4266-860c-750d56e2252a.png`.
- Updated all decision nodes in the risk query, restore purchase and membership subscription flowcharts from rounded rectangles to bordered diamonds.
- Increased the flow canvas minimum width, center decision column, horizontal branch gaps, map padding and vertical connector height.
- Moved `是 / 否` branch labels into dedicated 44 px connector clearance with opaque backgrounds, borders and foreground stacking so labels no longer sit beneath or overlap nodes.
- Long decision copy wraps inside the protected center area of each diamond.
- Narrow layouts retain a single-column fallback; document and canvas containers use scrolling instead of clipping the enlarged diagrams.
- Visually checked `#doc-flow-subscribe`, `#doc-flow-restore` and `#doc-flow-risk` in the in-app browser; the restore flow confirms the side label, dashed branch and diamond remain visually separated.
- JavaScript syntax and whitespace checks passed.

No actionable P0, P1, or P2 issues remain in the requested scope.

final result: passed

## Incremental QA · module-level requirement annotations

- Reference: `/var/folders/nd/rgv0xnnj307gldjrz406j18h0000gn/T/codex-clipboard-e280922c-cf37-45f7-8040-2afecff81951.png`.
- Replaced the former page-level annotation with independent annotations for each functional module in the English and Chinese prototypes.
- Default state exposes only a small cyan point; overview, data source, preconditions, result, display limit and sorting stay hidden until the point is selected.
- The point uses a restrained ripple animation, a 44 × 44 px interaction target, keyboard focus styling and a `prefers-reduced-motion` fallback.
- Verified the Home and Destination Risk Result screens in the in-app browser at `?v=37#home` and `?v=38#risk-result`.
- Verified English and Chinese dialogs independently; labels and descriptions follow the locale of the selected prototype.
- The point is positioned per module without changing the module's primary click action; modal close and subsequent point selection remain operable.
- JavaScript syntax check passed after removing obsolete page-level annotation code.

No actionable P0, P1, or P2 issues remain in the requested scope.

final result: passed

## Incremental QA · native flowchart redraw

- Replaced all three external flowchart iframes with native HTML/CSS flow diagrams inside `index.html`.
- Source topology was checked against the original Axure pages for risk query, purchase restoration and membership subscription.
- Risk query keeps the failed-generation retry loop and successful client-render path.
- Purchase restoration keeps the confirmation, deleted-account check, blocked restoration toast and subscription re-fetch path.
- Membership subscription keeps payment cancellation, payment failure and active-plan overwrite branches.
- The risk diagram retains model and JSON field documentation but deliberately redacts the plaintext API key.
- Each diagram includes text alternatives through `role="img"` and descriptive `aria-label` attributes; branch meaning is expressed with labels as well as color.
- Visual verification completed in the in-app browser at `#doc-flow-risk`, `#doc-flow-restore` and `#doc-flow-subscribe`.
- Responsive stacking was added below 700 px; JavaScript syntax check passed and no iframe reference remains.

No actionable P0, P1, or P2 issues remain in the requested scope.

final result: passed

## Incremental QA · bilingual interaction and prototype annotations

- Verified the current build at `http://localhost:8766/摄像头监测原型/?v=31#profile` and `#recharge` in the Codex in-app browser.
- The project tree now contains one `我的` node only, with `注销账号` and `订阅会员` beneath it.
- English profile displays `User nickname*****`; Chinese profile displays `用户昵称*****`; neither profile header contains a phone number.
- Both prototype columns expose the same interactive controls. The Chinese membership entry successfully navigated both columns to the standalone recharge page.
- Every prototype screen has a pulsing information control. The Chinese Profile control opened a localized modal with page overview, data source, preconditions, post-result, display limit and sorting rule.
- Changelog contains exactly one record: `2026/9/16 · 1.0.0 · 新增 · 新增 1.0.0 原型。`
- JavaScript syntax check passed with no errors.

No actionable P0, P1, or P2 issues remain in the requested scope.

final result: passed

## Incremental QA · remove linked-phone setting

- Source annotation: `/var/folders/nd/rgv0xnnj307gldjrz406j18h0000gn/T/codex-clipboard-cb051fa9-0da7-478b-adbd-c0a04c7c6dee.png`.
- Rendered implementation: `http://localhost:8766/AI原型/?v=19#profile`, inspected in the Codex in-app browser at the bilingual comparison viewport.
- Copy/content: removed only the `Phone number / 绑定手机号` settings row; retained the masked account identifier in the profile header, Privacy Policy, User Agreement, and Delete Account.
- Interaction cleanup: removed the obsolete linked-phone toast branch and translation entry; the account-deletion entry and flow remain intact.
- Responsive layout: compact profile spacing below 340 px container width keeps all three remaining settings rows visible above the bottom navigation in both locales.
- Regression check: English and Chinese profile screens remain aligned, with no clipping, unwanted gap, or change to nearby account information.

No actionable P0, P1, or P2 differences remain.

final result: passed

## Incremental QA · account-deletion continuation

- Source visual truth: `http://localhost:8766/原型文件/注销账号.html`, original Axure board with two 375 × 667 px mobile states.
- Rendered implementation: `http://localhost:8766/AI原型/?v=16#account-delete-read`, inspected in Codex in-app browser tab 18 at a 1265 × 710 CSS-pixel browser surface, device scale factor 1.
- Normalization: the two Axure states were compared with the same two product states adapted to the approved 402 × 874 CSS-pixel iPhone 17 screen. Device chrome and the surrounding bilingual canvas were excluded from content fidelity judgments.
- Compared states: Account Deletion agreement with disabled countdown, enabled Agree & Continue, Deletion Notes confirmation, Delete Now, and return-to-home feedback.
- Full-view evidence: the implementation preserves the source's two-step structure—agreement first, destructive confirmation second—and keeps the destructive action near the bottom of the screen.
- Focused evidence: the 10-second delay, three source consequences, close/back actions, Deletion Notes title and Delete Now action are all present in English and Chinese.
- Typography: long warning text remains readable without clipping; hierarchy distinguishes page title, warning title, consequences and destructive action.
- Spacing/layout: agreement and confirmation cards stay within the phone viewport; bottom navigation is hidden during this destructive flow to match the focused source state.
- Colors/tokens: the existing product teal is used for agreement progression and semantic red is used for irreversible deletion.
- Image quality: no new illustrative assets were required; existing vector navigation and close icons remain sharp.
- Copy/content: source consequences are preserved—login becomes unavailable, deletion is irreversible, regulated information removal applies; final prototype feedback also states the source annotation outcomes of phone-number unlinking and purchase restoration becoming unavailable.
- Interaction verification: both tree and profile entry points open the agreement; countdown unlocks at 0; Agree & Continue opens confirmation; close/back cancels; Delete Now returns home with the specified consequences.

No actionable P0, P1, or P2 differences remain.

final result: passed

## Incremental QA · electronic-record creation and management

- Source visual truth: `http://localhost:8766/原型文件/电子档案备份.html`, original Axure artboard at 375 × 767 px per mobile state.
- Rendered implementation: `http://localhost:8766/AI原型/?v=13#vault`, inspected in Codex in-app browser tab 15 at a 1265 × 710 CSS-pixel browser surface, device scale factor 1.
- Normalization: the Axure wireframe content was compared against the requested 6.3-inch iPhone 17 presentation. The source's 375 × 767 content was proportionally adapted to the implementation's 402 × 874 CSS-pixel device screen; surrounding project tree and bilingual comparison canvas were excluded from fidelity judgments.
- Compared states: document list, selected Manage state, Rename Record dialog, Confirm Delete dialog, Add New Digital Record form, upload-source sheet, required-field error, and Picture view.
- Full-view evidence: the implementation preserves the source hierarchy of encrypted-local-storage notice, My Documents list, per-record thumbnails, per-record Manage action, and add-record entry while using the established polished visual system.
- Focused evidence: Add includes Document Name, ID Card/Passport/Visa presets, Upload Image, maximum 5 images, 20 MB per file, JPG/PNG restriction and Create; Manage exposes Delete/Rename/Cancel; Delete and Rename dialogs reproduce the source copy and decisions; image thumbnails open Picture with Save to Photos.
- Typography: source labels and action hierarchy remain readable at the iPhone 17 scale; long English titles wrap without clipping.
- Spacing/layout: cards, thumbnail rows, action links, form fields and dialogs remain inside the phone viewport and scroll where the source list exceeds the visible area.
- Colors/tokens: intentionally inherit the approved teal/blue prototype styling instead of the Axure grayscale wireframe; semantic delete styling remains red.
- Image quality: the original uses generic image placeholders; the implementation uses the existing icon system for mock records and real image previews for user-selected JPG/PNG files.
- Copy/content: source field names, validation constraints, confirmation language and action labels are preserved; invented update dates and image-count labels were removed.
- Interaction verification: preset fills the name field; empty Create focuses the required name; upload opens Import from Photos/Take Photo; Manage exposes row actions; Rename opens with the current name; Confirm Delete removes the record; thumbnail opens the full-size view.

## Comparison history

- Pass 1: no actionable P0/P1/P2 mismatch was found. Existing visual styling and the larger device geometry are intentional project constraints, not source-flow drift.

## Follow-up polish

- P3: the source uses raster-like picture placeholders, while built-in record samples use the prototype's existing document icons. Real selected files render as image thumbnails.

final result: passed

## Incremental QA · source flows, bilingual comparison and scan-result fidelity

- Scan reference: `/var/folders/nd/rgv0xnnj307gldjrz406j18h0000gn/T/codex-clipboard-76319cd3-aa58-4f4a-8d3f-0c1911dbace3.png` (1027 × 826 px).
- Implementation evidence: Codex in-app browser at `http://localhost:8766/AI%E5%8E%9F%E5%9E%8B/?v=8#scan-results`.
- Verified states: English/Chinese scan-result comparison, Computer-row transition, and English/Chinese device-distance detail.
- Content fidelity: device types, device identifier, risk levels, distance bands, Suspicious labels, Computer detail type, and `0.56m` value match the supplied source. Only the Computer row is interactive, following the source flow arrow.
- Flow fidelity: 风险查询流程图、恢复购买流程、订阅会员流程 are embedded directly from the original Axure HTML files; their nodes and flow copy are not rewritten.
- Requirements interaction: each requirement row exposes a pulsing information point; its modal separates the source description from clearly labelled supplemental data-source, precondition, postcondition, display-limit, and sorting suggestions.
- Bilingual behavior: navigation changes the English prototype and read-only Chinese comparison to the same screen.
- Removed content: the promotional hero copy, promotional profile footer, Vancouver example, and hard-coded risk explanation are absent.

## Comparison history

- Pass 1: scan-result field values clipped in the narrow dual-phone viewport.
- Pass 2: responsive result-card sizing and wrapping restored all source fields in both phones without horizontal overflow.

No actionable P0, P1, or P2 differences remain for the supplied scan-result content and field layout.

final result: passed

## Incremental QA · navigation, documents and device sizing

- Official device reference: Apple iPhone 17 technical specifications — 6.3-inch display, 2622 × 1206 px, 149.6 × 71.5 mm.
- Browser evidence: Codex in-app browser tab 8 at `http://localhost:8766/?v=4`.
- Device geometry: 418 × 890 CSS px outer frame at full scale; 8 px frame produces a 402 × 874 CSS px screen, matching the 3× logical size inferred from 1206 × 2622 px. Smaller browser windows scale both dimensions proportionally.
- Navigation styling: colored group hierarchy, selected-state accent, search surface and header gradient verified.
- Document pages verified: 更新日志、需求列表 v1.0.1、需求列表 v1.0.0 all open from the tree and expose semantic tables.
- Transition verified: selecting 首页 after a document restores the mobile prototype.
- Accessibility check: folder expansion state, selected document rows, table headings and phone navigation remain exposed in the browser accessibility tree.

final result: passed

## Incremental QA · 2026-09-16

- Change reference: `/var/folders/nd/rgv0xnnj307gldjrz406j18h0000gn/T/codex-clipboard-23b572eb-1815-47ad-a777-a661b06ed2cf.png`
- Browser evidence: Codex in-app browser tab 7 at `http://localhost:8766/?v=3`
- Verified state: home screen in the expanded desktop prototype.
- Result: the location/weather row and dark-mode control are absent; the hero now begins directly below the status bar with consistent spacing. Dark-theme variables, theme trigger logic, and the two unused header icons were removed.
- Regression check: project tree, home cards, and bottom navigation remain visible and operable.

final result: passed

## Incremental QA · concrete scan-device icons

- Source visual truth: `/var/folders/nd/rgv0xnnj307gldjrz406j18h0000gn/T/codex-clipboard-69cc5711-27f7-4308-b53c-c2e042cc4c6b.png` (701 × 338 px), with the three device-type tiles marked for replacement.
- Rendered implementation: `http://localhost:8766/AI原型/?v=15#scan-results`, inspected in Codex in-app browser tab 16 at a 794 × 684 CSS-pixel browser surface, device scale factor 1.
- State: English and Chinese Device Scan Result screens shown side by side.
- Full-view comparison: all three result cards retain their original proportions, field alignment, Suspicious labels, arrows and vertical rhythm.
- Focused comparison: the Phone, Computer and General text tiles are replaced by distinct mobile-phone, desktop-computer and multi-device assets; each remains centered in the same blue 36–44 px tile.
- Typography: no field typography or wrapping changed; device identification is now carried by icons with accessible labels.
- Spacing/layout: icon assets fit without widening the first grid column or clipping adjacent fields.
- Colors/tokens: Phosphor icons use the existing product blue `#3f7cf4` over the existing pale-blue device tile.
- Image quality: all three are local vector assets from Phosphor Icons Core 2.1.1, with no raster blur and no dependence on runtime network access.
- Copy/content: device fields and values are unchanged; only the visible device-type words were replaced as requested.
- Interaction regression: the Computer row remains clickable and still opens Device Distance Detection.

No actionable P0, P1, or P2 differences remain.

final result: passed

## Incremental QA · remove Safety brief block

- Source visual truth: `/var/folders/nd/rgv0xnnj307gldjrz406j18h0000gn/T/codex-clipboard-83fac12d-068e-4ede-940b-c5aa0d4fe755.png` (514 × 302 px), identifying the complete `Safety brief / Pre-trip checklist` region for removal.
- Implementation screenshot: `/private/tmp/safe-me-home-v20.png` (794 × 684 px), captured from Codex in-app browser tab 20 at `http://localhost:8766/AI原型/?v=20#home`, device scale factor 1.
- State: English and Chinese home prototypes displayed side by side.
- Full-view comparison: the identified section title, action, information card, icon and descriptive copy are absent from both locales; the home feature grid remains intact.
- Focused comparison: the supplied crop and the rendered home view were opened together; no part of the marked block remains and no empty spacer was introduced after the final feature card.
- Typography: unrelated headings, card labels, weights and wrapping are unchanged.
- Spacing/layout: content now ends naturally after `Your safety hub`; existing phone geometry and bottom navigation are unchanged.
- Colors/tokens and image quality: no unrelated tokens or assets were modified.
- Copy/content: removed the English strings and their Chinese translation entries; no stale accessible text remains.
- Comparison history: initial post-change capture contained no actionable P0, P1 or P2 mismatch, so no corrective iteration was required.

No actionable P0, P1, or P2 differences remain.

final result: passed

## Incremental QA · project tree navigation redesign

- Source visual truth: `/var/folders/nd/rgv0xnnj307gldjrz406j18h0000gn/T/codex-clipboard-11354734-ae49-4f45-9369-3368ecd7f3a5.png` (216 × 688 px), used as the content and hierarchy reference while visual styling was intentionally redesigned.
- Implementation screenshot: `/private/tmp/safe-me-sidebar-v22.png` (794 × 684 px), captured from Codex in-app browser tab 21 at `http://localhost:8766/AI原型/?v=22#scan-results`, device scale factor 1.
- State: expanded project tree beside the bilingual Device Scan Result prototype, with 首页 selected.
- Full-view comparison: every original group, nested item and indentation level remains present; the panel is widened from 220 px to 264 px for clearer hierarchy and labels.
- Focused comparison: the original and implementation were opened together. The redesign adds a branded header, refined search field, color-coded group surfaces, connection rails, rounded hover/selected states and a calmer scrollbar without changing tree order.
- Typography: compact 12.5–14 px interface type retains Chinese readability, with stronger group and selected-row weights.
- Spacing/layout: 4/8 px rhythm, 36–40 px rows and 14 px indentation steps improve scanability without clipping labels.
- Colors/tokens: teal brand surfaces align with the mobile prototype; purple, teal, amber and blue remain supporting hierarchy colors with text-plus-icon cues.
- Image quality: all navigation imagery uses the existing local vector icon system; no raster or placeholder assets were introduced.
- Copy/content: node names and order are unchanged; only the small `PRODUCT MAP` context label was added.
- Interaction verification: requirements group collapsed and expanded successfully; search filtered to 电子档案; selecting the result navigated to `#vault`; visible focus, hover, pressed and selected states remain available.
- Responsive regression: the existing mobile breakpoint still hides the desktop tree below 700 px; desktop content remains contained without horizontal overflow.
- Comparison history: the first rendered pass had no actionable P0, P1 or P2 issue, so no corrective visual iteration was required.

No actionable P0, P1, or P2 differences remain within the requested redesign scope.

final result: passed

## Incremental QA · destination risk result flow

- Source of truth: `原型文件/目的地风险查询.html` and `原型文件/风险查询流程图.html`.
- Added the original post-submit loading state and the result state to both English and Chinese prototypes.
- Result content preserves the original five fields: Destination, Security Level, Natural-Hazard Alerts, Scam & Violent-Incident Alerts, and Local Customs & Cultural Taboos.
- The Vancouver example copy is reproduced from the original file; no new risk category or scenario was invented.
- Interaction verified in the in-app browser: entering `Vancouver` and submitting transitions through loading to `#risk-result` after 1.1 seconds.
- Both language columns display their matching localized content and provide a direct route back to the query page.
- The two new screens include the existing prototype information-dot dialog.
- JavaScript syntax check passed; reduced-motion rules already cover the new loading animation.

No actionable P0, P1, or P2 issues remain in the requested scope.

final result: passed
