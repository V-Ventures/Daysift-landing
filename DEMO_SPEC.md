# Daysift Landing Page Demo - Development Spec

## Overview
An auto-playing, animated demo showcase for the Daysift landing page, inspired by Raycast's feature carousel. The demo shows Daysift running inside a Chrome browser window for context awareness.

---

## Demo Structure

### 5 Feature Slides

| # | Slide Name | Feature | What to demonstrate |
|---|------------|---------|---------------------|
| 1 | **Search** | Core search | Type "Q3 budget" → show results: Google Doc, Google Sheet, Miro board with favicons |
| 2 | **Filters** | Filter pills | Show all results → click "Google Docs" filter → results narrow |
| 3 | **AI Search** | AI answers | Type "how do I center a div?" → AI answer appears with formatted response |
| 4 | **Notes** | Notes + AI | Show notes list → click into "Meeting notes" → show AI writing inside note |
| 5 | **Commands** | Quick actions | Show / command menu → list of actions (New Doc, New Sheet, New Miro, etc.) |

---

## Visual Design

### Chrome Browser Wrapper
```
┌─────────────────────────────────────────────────────────────┐
│ ● ● ●    ◄ ► ↻  │ 🔒 app.example.com           │ ☆  ⋮  │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│                    (blurred/dimmed page)                    │
│                                                             │
│         ┌─────────────────────────────────────┐            │
│         │      DAYSIFT MODAL OVERLAY          │            │
│         │                                     │            │
│         │  [Search input with typing...]      │            │
│         │                                     │            │
│         │  [Results / Content area]           │            │
│         │                                     │            │
│         │  [Footer with shortcuts]            │            │
│         └─────────────────────────────────────┘            │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Animations
1. **Typing animation**: Characters appear one by one (50-80ms per char)
2. **Cursor blink**: Blinking cursor at end of input
3. **Results fade-in**: Results appear with staggered fade-in
4. **Slide transitions**: Smooth crossfade between slides (500ms)
5. **Auto-advance**: Each slide shows for 4-5 seconds before advancing

### Slide Switcher (below demo)
Five clickable buttons to manually switch slides:
`[Search] [Filters] [AI Search] [Notes] [Commands]`

---

## Detailed Slide Specs

### Slide 1: Search
**Input animation**: Type "Q3 budget" character by character
**Results to show**:
- 📄 Q3 Budget Planning - Google Docs - 2 days ago
- 📊 Q3 Budget Spreadsheet - Google Sheets - 1 week ago
- 🎨 Q3 Budget Review - Miro - 3 days ago

**Filter pills visible**: All, Google Docs, Google Sheets, Notion, Figma, Miro

### Slide 2: Filters
**State**: Shows "Q3 budget" already typed
**Animation**:
1. "Google Docs" pill gets selected (highlight animation)
2. Results filter down to just Google Docs items
**Results after filter**:
- 📄 Q3 Budget Planning - Google Docs - 2 days ago
- 📄 Q3 Budget Draft - Google Docs - 1 week ago

### Slide 3: AI Search
**Input animation**: Type "how do I center a div in CSS?"
**Badge**: "Ask AI" badge appears on right of input
**Animation**: Press enter → loading state → AI answer fades in
**AI Answer content**:
```
To center a div, use Flexbox:

.container {
  display: flex;
  justify-content: center;
  align-items: center;
}

Or use Grid:

.container {
  display: grid;
  place-items: center;
}
```

### Slide 4: Notes
**Three-part animation**:

**Part A - Notes list**:
- Show /notes command result
- List: "Meeting notes", "Project ideas", "Weekly standup"

**Part B - Open note**:
- Click into "Meeting notes"
- Show note content with title and body text

**Part C - AI in notes**:
- Show AI prompt appearing
- AI generates/suggests text within the note

### Slide 5: Commands
**Input**: Show "/" typed
**Results - Command list**:
- ✨ New Google Doc
- 📊 New Google Sheet
- 🎨 New Miro Board
- 📝 New Notion Page
- 📋 New Note
- ⚙️ Settings

---

## Development Phases

### Phase 1: Foundation
Build the base container and Chrome wrapper

### Phase 2: Static Slides
Create all 5 slides as static HTML/CSS (no animation)

### Phase 3: Slide Switching
Add manual slide switcher functionality

### Phase 4: Typing Animation
Add character-by-character typing with cursor

### Phase 5: Results Animation
Add staggered fade-in for results

### Phase 6: Auto-play
Add automatic slide advancement with timing

### Phase 7: Polish
Transitions, timing tweaks, responsive design

---

## User Stories & Tasks

### Epic 1: Demo Foundation

#### US-1.1: Chrome Browser Wrapper
**As a** visitor to the landing page
**I want to** see Daysift in context of a browser window
**So that** I understand it's a browser extension

**Tasks**:
- [ ] Create `.demo-browser` container with browser chrome styling
- [ ] Add window controls (red/yellow/green dots)
- [ ] Add address bar with lock icon and URL
- [ ] Add tab bar with one active tab
- [ ] Add dimmed/blurred background page behind modal
- [ ] Style to match dark theme (similar to Raycast screenshots)

**Acceptance Criteria**:
- Browser window looks realistic
- Modal floats centered over dimmed background
- Responsive on mobile (can simplify chrome)

---

#### US-1.2: Demo Container Structure
**As a** developer
**I want to** have a clean container structure
**So that** slides can be swapped easily

**Tasks**:
- [ ] Create `.demo-showcase` main container
- [ ] Create `.demo-slide` wrapper for each slide
- [ ] Create `.demo-switcher` for the 5 buttons below
- [ ] Set up CSS for showing/hiding slides
- [ ] Replace existing demo section in index.html

**Acceptance Criteria**:
- Only one slide visible at a time
- Switcher buttons are clickable
- Structure supports future animations

---

### Epic 2: Static Slides

#### US-2.1: Search Slide (Static)
**As a** visitor
**I want to** see the search feature demonstrated
**So that** I understand Daysift finds my work documents

**Tasks**:
- [ ] Create search input with "Q3 budget" pre-filled
- [ ] Create filter pills row (All, Docs, Sheets, etc.)
- [ ] Create 3 result items with favicons and metadata
- [ ] Style results list matching current Daysift design
- [ ] Add footer with keyboard shortcuts

**Acceptance Criteria**:
- Matches current Daysift modal styling
- Shows realistic work documents
- Favicons visible for each source

---

#### US-2.2: Filters Slide (Static)
**As a** visitor
**I want to** see how filters work
**So that** I understand I can narrow results by source

**Tasks**:
- [ ] Copy search slide structure
- [ ] Show "Google Docs" pill as selected/active
- [ ] Show filtered results (only Docs items)
- [ ] Visual indicator on active filter

**Acceptance Criteria**:
- Clear visual difference showing filter is active
- Results visibly reduced to match filter

---

#### US-2.3: AI Search Slide (Static)
**As a** visitor
**I want to** see AI search capability
**So that** I understand Daysift can answer questions

**Tasks**:
- [ ] Create search input with question text
- [ ] Add "Ask AI" badge to input area
- [ ] Create AI answer view (different from results list)
- [ ] Show formatted answer with code blocks
- [ ] Style answer area distinctly

**Acceptance Criteria**:
- Question clearly visible in input
- "Ask AI" badge prominent
- Answer formatted with code styling
- Visually distinct from regular search

---

#### US-2.4: Notes Slide (Static)
**As a** visitor
**I want to** see the notes feature
**So that** I understand Daysift stores notes locally

**Tasks**:
- [ ] Create notes list view
- [ ] Create single note detail view
- [ ] Create AI-in-notes view (showing AI assistance)
- [ ] Decide: show all 3 states or just one
- [ ] Style note content area

**Acceptance Criteria**:
- Notes feature clearly demonstrated
- Shows both list and detail views
- AI assistance in notes visible

---

#### US-2.5: Commands Slide (Static)
**As a** visitor
**I want to** see quick commands
**So that** I understand Daysift has shortcuts to create docs

**Tasks**:
- [ ] Create command input with "/" shown
- [ ] Create command list with icons
- [ ] Show 5-6 commands (New Doc, New Sheet, etc.)
- [ ] Style command items with icons

**Acceptance Criteria**:
- Command palette clearly visible
- Actions are recognizable (create new docs)
- Icons match the sources

---

### Epic 3: Interactivity

#### US-3.1: Slide Switcher
**As a** visitor
**I want to** click buttons to switch demo slides
**So that** I can explore features at my own pace

**Tasks**:
- [ ] Create 5 switcher buttons with labels
- [ ] Add click handlers to switch slides
- [ ] Add active state styling to current button
- [ ] Smooth transition between slides

**Acceptance Criteria**:
- Clicking button shows corresponding slide
- Active button is visually highlighted
- Transition is smooth (not jarring)

---

### Epic 4: Animations

#### US-4.1: Typing Animation
**As a** visitor
**I want to** see text being typed
**So that** the demo feels alive and realistic

**Tasks**:
- [ ] Create typing animation function
- [ ] Add blinking cursor element
- [ ] Implement character-by-character reveal
- [ ] Set appropriate timing (50-80ms per char)
- [ ] Trigger typing when slide becomes active

**Acceptance Criteria**:
- Text types naturally (not too fast/slow)
- Cursor blinks at end
- Animation restarts when revisiting slide

---

#### US-4.2: Results Fade-in
**As a** visitor
**I want to** see results appear smoothly
**So that** it feels like real search behavior

**Tasks**:
- [ ] Add staggered fade-in animation for results
- [ ] Results appear one after another (100ms delay)
- [ ] Animate after typing completes

**Acceptance Criteria**:
- Results don't all appear at once
- Stagger feels natural
- Coordinates with typing animation

---

#### US-4.3: Auto-play Carousel
**As a** visitor
**I want to** see the demo play automatically
**So that** I can watch without clicking

**Tasks**:
- [ ] Set up auto-advance timer
- [ ] Each slide displays for 4-5 seconds
- [ ] Progress indicator on switcher buttons
- [ ] Pause on hover or manual interaction
- [ ] Resume after inactivity

**Acceptance Criteria**:
- Demo cycles through all slides
- Timing feels comfortable (not rushed)
- User can interrupt and take control
- Resumes auto-play after idle

---

### Epic 5: Polish

#### US-5.1: Transitions & Timing
**As a** visitor
**I want to** smooth transitions between states
**So that** the demo feels polished

**Tasks**:
- [ ] Fine-tune all animation timings
- [ ] Add crossfade between slides
- [ ] Ensure animations don't overlap awkwardly
- [ ] Test on different screen sizes

**Acceptance Criteria**:
- No janky or jarring transitions
- Timings feel natural
- Works on mobile

---

#### US-5.2: Responsive Design
**As a** mobile visitor
**I want to** see the demo on smaller screens
**So that** I can understand the product on any device

**Tasks**:
- [ ] Simplify Chrome wrapper on mobile
- [ ] Scale modal appropriately
- [ ] Ensure switcher buttons work on touch
- [ ] Test on various breakpoints

**Acceptance Criteria**:
- Demo visible and functional on mobile
- Not broken on tablet sizes
- Touch interactions work

---

## Technical Implementation Notes

### File Structure
```
landing/
├── index.html (modify existing demo section)
└── demo/
    ├── demo.css (all demo-specific styles)
    └── demo.js (animation and interaction logic)
```

### CSS Classes
```css
.demo-showcase        /* Main container */
.demo-browser         /* Chrome window wrapper */
.demo-browser-chrome  /* Tab bar and address bar */
.demo-browser-content /* Dimmed page background */
.demo-modal           /* Daysift modal overlay */
.demo-slide           /* Individual slide container */
.demo-slide.active    /* Currently visible slide */
.demo-switcher        /* Button row below demo */
.demo-switcher-btn    /* Individual switcher button */
.demo-switcher-btn.active /* Currently active button */
.demo-typing-cursor   /* Blinking cursor */
```

### JavaScript Functions
```javascript
// Core functions needed
initDemo()           // Initialize demo on page load
switchSlide(index)   // Switch to specific slide
startAutoPlay()      // Begin auto-advance
pauseAutoPlay()      // Pause on interaction
typeText(element, text, callback)  // Typing animation
fadeInResults(container)           // Staggered results
```

---

## QA Checklist (per slide)

### Functionality
- [ ] Slide displays correctly
- [ ] Content matches spec
- [ ] Animations play smoothly
- [ ] No console errors

### UX Quality
- [ ] Feels realistic and polished
- [ ] Timing feels natural
- [ ] Clear what feature is being shown
- [ ] Matches Daysift brand/colors

### Responsive
- [ ] Works on desktop (1200px+)
- [ ] Works on tablet (768px-1199px)
- [ ] Works on mobile (320px-767px)

### Cross-browser
- [ ] Chrome
- [ ] Safari
- [ ] Firefox

---

## Definition of Done

A slide is complete when:
1. Static version reviewed and approved
2. Animations implemented and smooth
3. QA checklist passed
4. Integrated into auto-play carousel
5. Responsive on all breakpoints
