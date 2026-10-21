# PR #631 review evidence

Before: original PR head `1536db77d04bbd53d832e1f20db02d503eca2516`, Next.js 16.2.2.
After: corrected PR head `e607713`, rebased onto main `97c6923`, Next.js 16.4.2.
Both production builds ran in Chromium at 1280×800. Client transaction-feed responses were stubbed empty; server feed failure uses the application's existing empty-state fallback. No live payment was sent.

`before-browser.json` reproduces opacity 1 before the root margin and a sudden decrease during scroll. `after-browser.json` proves opacity 0 at 30px inside the viewport and a monotonic fade to 1, with inline styles and animation removed on completion. Reduced-motion and no-JavaScript screenshots keep the sections visible. The after check also tests preference changes both while waiting and during a fade, and scrolls through all enhanced sections.

Screenshot filenames encode before/after, motion setting, and scroll/animation stage. The 30px frames show the leading edge of the section; complete frames show its final visible layout.
