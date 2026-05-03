# Design Spec: ExamWiki Flagship (Textbook Monolith)

## 1. Feature Summary
A high-yield interactive study ecosystem for KTU CST362 students. It delivers all 5 modules of Python notes in a single, authoritative, two-column reading environment optimized for high-speed retrieval under exam pressure.

## 2. Primary User Action
Instantly locating a specific algorithm or concept (e.g., "Armstrong logic") and understanding its exam application in under 10 seconds.

## 3. Design Direction (Editorial Authority)
- **Aesthetic**: Luxury Editorial / Academic Textbook.
- **Typography**: `Instrument Serif` (Italic) for headings to establish authority; `DM Sans` for body text to ensure readability.
- **Tone**: Calm, structured, and zero-to-hero depth (Still Water persona).
- **Colors**: Warm Paper Light (`#F5F4F0`) / Deep Midnight Dark (`#09090B`).
- **Interaction**: Physical-feel interactions (`scale 0.97` on active) and hardware-accelerated transitions.

## 4. Layout Strategy (2-Column "Command & Well")
- **Sidebar (Left - 320px)**: Sticky and persistent. Contains the global Module tree and local Table of Contents. Automatically highlights the current sub-section using `IntersectionObserver`.
- **Reading Well (Right - Flex)**: Centered reading column with a hard `max-width: 800px`. Use the extra right gutter for "Floating Frequency Badges".
- **Header (52px)**: Glassmorphic with a reading progress bar pinned to the very top.

## 5. Data Architecture (Monolith)
- **Database (`data.js`)**: All 5 modules stored as complete strings in a JSON-like array.
- **Rendering**: Dynamic injection on page load. No network fetches for content after initial load.
- **Search**: Headings and summaries indexed for the ⌘K Command Palette.

## 6. Key Components
- **Module Accordions**: Collapsible sections in the content area to prevent "wall of text" fatigue.
- **Code Blocks**: Fixed dark theme (`#0D1117`) with a custom copy-to-clipboard header.
- **Frequency Badges**: Tiered signaling (HIGH/MED/LOW) using `JetBrains Mono`.
- **Callouts**: Tinted boxes for "Analogy", "Exam Tip", and "Definition".

## 7. Interaction Model
- **Click**: Sidebar links smooth-scroll to content.
- **Scroll**: IntersectionObserver updates Sidebar active state and Header breadcrumb.
- **Search (⌘K)**: Opens a blurred modal overlay for instant heading search.
- **Physicality**: All buttons use `cubic-bezier(0.23, 1, 0.32, 1)` for snappy, premium movement.

## 8. Content Requirements
- **Complete Notes**: 100% of the text from Modules 1-5 must be present.
- **Metadata**: Each section requires a "Frequency" level and a "Summary" line.

## 9. Recommended References
- `impeccable/reference/typography.md` (for Instrument Serif pairing)
- `impeccable/reference/spatial-design.md` (for the 2-column grid)
- `emil-design-eng/SKILL.md` (for the scale-on-press and easing curves)

---
*Spec written: 2026-05-03*
