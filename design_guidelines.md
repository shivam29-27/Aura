# KindMind Design Guidelines

## Design Approach
**System-Based with Accessibility-First Principles**

Using Material Design as the foundation, heavily customized for maximum accessibility and empathy-driven interactions. Drawing additional inspiration from inclusive design leaders like Microsoft's Inclusive Design toolkit and BBC's accessibility standards.

**Core Design Principles:**
1. Maximum accessibility without compromise
2. Empathy through thoughtful interactions
3. Clarity over decoration
4. Adaptive and personalized experiences

---

## Typography System

**Font Family:**
- Primary: Inter (via Google Fonts CDN) - exceptional readability across sizes
- Monospace: JetBrains Mono - for code/technical content

**Type Scale (Desktop):**
- Hero/H1: text-6xl (60px), font-bold, leading-tight
- H2: text-4xl (36px), font-semibold, leading-snug
- H3: text-3xl (30px), font-semibold
- H4: text-2xl (24px), font-medium
- Body Large: text-xl (20px), font-normal, leading-relaxed
- Body: text-lg (18px), font-normal, leading-relaxed
- Small: text-base (16px), font-normal

**Mobile Scaling:** Reduce by one size tier (e.g., H1 becomes text-5xl)

**Accessibility Requirements:**
- Minimum body text: 18px (text-lg)
- Line height: 1.6-1.8 for all body text
- Letter spacing: tracking-wide for headings, tracking-normal for body
- Never use font-weight below 400

---

## Layout System

**Spacing Primitives:**
Core spacing units: **4, 6, 8, 12, 16, 20, 24** (Tailwind scale)
- Micro spacing (within components): p-4, gap-4, space-y-6
- Component spacing: p-8, mb-12, gap-8
- Section spacing: py-20, my-24
- Large breaks: py-32

**Container Strategy:**
- Max width: max-w-7xl for content sections
- Text content: max-w-4xl for optimal readability
- Dashboard cards: max-w-sm to max-w-md
- Full-width sections with inner containers

**Grid Systems:**
- Dashboard: grid-cols-1 md:grid-cols-2 lg:grid-cols-3
- Feature showcase: grid-cols-1 md:grid-cols-2
- Mobile-first: Always single column on mobile

**Vertical Rhythm:**
- Hero section: 85vh minimum
- Content sections: py-20 on desktop, py-12 on mobile
- Consistent section dividers with generous padding

---

## Component Library

### Navigation
**Header:**
- Sticky header with backdrop-blur effect
- Height: h-20
- Logo + text navigation links + accessibility controls group
- Quick access: Text size toggle, High contrast toggle, Keyboard shortcuts icon
- Mobile: Hamburger menu with full-screen overlay

### Hero Section
**Layout:**
- Split layout: 60% text (left), 40% visual (right)
- Text side: H1 + subtitle (text-xl) + 2-button CTA group + trust indicator
- Visual side: Large illustration/image showing diverse users interacting with AI
- Background: Subtle gradient overlay

**Images:**
- Hero image: Diverse group of people using assistive technology with AI interfaces
- Shows inclusion: wheelchair user, sign language user, person with guide dog
- Warm, welcoming, professional photography style

### Dashboard Cards
**Structure:**
- Rounded corners: rounded-2xl
- Padding: p-8
- Shadow: shadow-lg with hover:shadow-xl transition
- Border: 2px solid with subtle border treatment
- Icon (top) + Title (H4) + Description + Action button/link

**Card Types:**
1. Mood Journal Card: Icon, "Today's Reflection", quick entry field, "View History" link
2. Accessibility Score Card: Large number display, progress indicator, "Improve Score" CTA
3. Sign Translation Card: Webcam preview, status indicator, "Start Translation" button
4. Quick Action Cards: Icon + Label + Single action button

### Forms & Inputs
**Input Fields:**
- Height: h-14 (56px) - large touch targets
- Padding: px-6, py-4
- Border: 3px border (increased from standard 1px)
- Focus state: ring-4 with high contrast ring
- Labels: Always visible above input, text-lg font-medium

**Buttons:**
- Primary: h-14, px-8, text-lg, rounded-xl, font-semibold
- Secondary: h-14, px-8, text-lg, rounded-xl, font-medium, border-2
- Icon buttons: min 48x48px touch target
- Loading state: Spinner with descriptive text

**When on images:** Add backdrop-blur-md and semi-transparent background

### Feature Sections
**Multi-Feature Display:**
- Grid layout: 2 columns on desktop, single column mobile
- Each feature: Large icon (96x96px), H3 title, 2-3 sentence description
- Icons: Use Heroicons via CDN, 2xl size minimum
- Spacing between features: gap-16

### Community Forum
**Thread Cards:**
- Avatar (left) + Username + Kindness Score badge
- Post preview with "Read more" expansion
- AI empathy indicator if present
- Action buttons: Like (heart icon), Reply, Share

### Accessibility Controls Panel
**Slide-out Panel (right side):**
- Width: w-96
- Backdrop: backdrop-blur-lg
- Controls:
  - Text size slider (with live preview)
  - Contrast mode toggle (Standard/High/Maximum)
  - Animation toggle (Reduce motion)
  - Screen reader mode toggle
  - Keyboard shortcuts reference
  - Voice control activation

---

## Interaction Patterns

**Focus Indicators:**
- All interactive elements: 4px focus ring, high contrast
- Skip to main content link (visible on focus)
- Focus trap in modals and panels

**Loading States:**
- Skeleton screens for content loading
- Progress indicators for AI processing
- Descriptive loading text ("Analyzing emotion...", "Processing sign language...")

**Gestures:**
- Visual feedback for gesture recognition (glowing outline)
- Confirmation before gesture-triggered actions
- Tutorial overlay on first use

**Animations:** Minimal, purposeful only
- Page transitions: Simple fade (200ms)
- Card hover: Subtle lift (shadow change)
- Success feedback: Gentle scale pulse
- Respect prefers-reduced-motion

---

## Responsive Breakpoints

- Mobile: < 768px (single column, simplified nav, stacked cards)
- Tablet: 768px - 1024px (2-column grids, adjusted spacing)
- Desktop: > 1024px (full layouts, 3-column grids)

---

## Accessibility Implementation

**ARIA:**
- Landmarks on all major sections (main, nav, aside, footer)
- Live regions for AI status updates
- Descriptive labels for all interactive elements
- Role attributes for custom components

**Keyboard Navigation:**
- Logical tab order throughout
- Escape to close modals/panels
- Arrow keys for navigation in grids/lists
- Custom shortcuts overlay (Shift + ?)

**Screen Reader:**
- Descriptive alt text for all images
- Hidden text for icon-only buttons
- Status announcements for AI actions
- Form validation messages read aloud

---

## Images

1. **Hero Section:** Large image (right side) showing diverse users engaging with AI accessibility tools - wheelchair user with gesture control, person using sign language translator, someone with assistive device. Professional, warm, inclusive photography.

2. **Feature Sections:** Icon-based (no photos), using Heroicons for consistency

3. **Community Section:** User avatars (generated or placeholder), optional profile photos

4. **Testimonials/Success Stories:** Real user photos showing diverse abilities and backgrounds