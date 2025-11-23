# Student Performance Analytics & Prediction System - Design Guidelines

## Design Approach

**Selected Framework:** Material Design (Data-focused variant)  
**Rationale:** Information-dense academic application requiring robust data visualization, clear hierarchy, and proven interaction patterns for complex dashboards and analytics interfaces.

**Key Design Principles:**
- Information clarity over decoration
- Data visualization as primary communication method
- Purposeful hierarchy for complex academic data
- Professional, trustworthy academic aesthetic

---

## Typography

**Font Stack:** Inter (via Google Fonts CDN)

**Hierarchy:**
- **Page Headers:** text-3xl font-bold (Dashboard titles, main sections)
- **Section Headers:** text-2xl font-semibold (Card titles, module headers)
- **Subsection Headers:** text-lg font-semibold (Table headers, chart titles)
- **Body Text:** text-base font-normal (General content, descriptions)
- **Data Points:** text-sm font-medium (Table cells, metric values)
- **Labels/Captions:** text-xs font-medium uppercase tracking-wide (Form labels, chart legends)
- **Emphasized Metrics:** text-4xl font-bold (Key statistics, GPA displays)

---

## Layout System

**Spacing Units:** Tailwind units of 4, 6, 8, 12, 16 (p-4, gap-6, mb-8, py-12, mt-16)

**Grid Structure:**
- Dashboard: 12-column grid (grid-cols-12) with responsive breakpoints
- Main content area: max-w-7xl mx-auto
- Sidebar navigation: Fixed 16rem width (w-64)
- Card grids: grid-cols-1 md:grid-cols-2 lg:grid-cols-3 for stat cards
- Data tables: Full-width within container with horizontal scroll on mobile

**Container Strategy:**
- App shell: Full viewport height (min-h-screen)
- Content sections: px-6 py-8 spacing
- Cards: p-6 consistent internal padding
- Form containers: max-w-2xl for optimal form width

---

## Component Library

### Navigation
**Top Bar:** Fixed header with app logo, global search, user profile dropdown, notifications icon  
**Sidebar:** Vertical navigation with icons + labels, collapsible on mobile, active state indicators, grouped sections (Dashboard, Students, Courses, Analytics, Predictions)

### Data Display
**Stat Cards:** Grid layout showing key metrics (Total Students, Average GPA, At-Risk Students, Course Completion Rate) with large numbers, labels, and trend indicators (↑↓)  
**Data Tables:** Sortable headers, alternating row backgrounds for readability, sticky headers, row hover states, pagination controls, inline action buttons  
**Charts:** Chart.js for line graphs (grade trends), bar charts (subject comparison), pie charts (grade distribution), donut charts (attendance breakdown) - all with legends and axis labels

### Forms & Inputs
**Text Inputs:** Full-width with floating labels, border focus states, helper text below  
**Dropdowns:** Custom select with search capability for long lists (student selection, course filters)  
**Date Pickers:** Material-style calendar overlays  
**File Upload:** Drag-and-drop zones for CSV imports with file preview

### Cards & Containers
**Dashboard Cards:** Elevated with subtle shadow (shadow-md), rounded corners (rounded-lg), white background  
**Module Cards:** Course cards with thumbnail placeholder, course code, student count, performance summary  
**Student Profile Cards:** Avatar placeholder, name, ID, key metrics in compact layout

### Interactive Elements
**Buttons:** 
- Primary: Filled with rounded corners (rounded-md px-4 py-2)
- Secondary: Outlined variant
- Icon buttons: Square with icon centering (w-10 h-10)
- All buttons: Font-medium text, subtle shadow on primary

**Tabs:** Underline-style active indicator, horizontal scrolling on mobile  
**Filters:** Chips/tags for active filters with remove icon, filter panel collapsible on mobile  
**Modals:** Centered overlay with backdrop blur, max-w-lg to max-w-2xl depending on content

### Feedback & States
**Loading States:** Skeleton screens for tables, shimmer effect for cards  
**Empty States:** Centered icon + message + action button  
**Alerts:** Toast notifications (top-right positioning), inline alerts for form validation  
**Progress Indicators:** Linear progress for uploads, circular for predictions processing

### Data Visualization Specifics
**Performance Charts:** Line charts showing semester-wise grade progression with gridlines  
**Comparison Views:** Side-by-side bar charts for subject performance  
**Prediction Results:** Confidence intervals displayed with shaded areas, predicted vs actual comparison  
**Attendance Heatmaps:** Calendar-style grid with intensity indicators

---

## Images

**Profile Avatars:** Circular placeholders (40px-64px) with initials fallback throughout the application  
**Course Thumbnails:** 16:9 rectangular placeholders for course cards  
**No Hero Image:** This is a dashboard application - login page uses simple centered form with subtle institutional branding area

---

## Layout Patterns

**Dashboard View:** 
- Top stats row with 4 metric cards (grid-cols-4)
- Middle section: 2-column layout (8/4 split) - main chart left, quick actions right
- Bottom section: Recent activity table full-width

**Student Detail Page:**
- Header: Student info card with photo, details, overall GPA
- Tabbed content: Performance, Attendance, Predictions
- Each tab: Charts + detailed tables

**Prediction Interface:**
- Form column (left 1/3): Input fields for prediction parameters
- Results column (right 2/3): Visualization of prediction with confidence metrics

**Data Tables:**
- Sticky header row
- Minimum 8 columns visible without scroll on desktop
- Action column always right-aligned
- Expand rows for details (accordion pattern)

---

## Responsive Behavior

- **Desktop (1024px+):** Full sidebar, multi-column layouts, expanded tables
- **Tablet (768px-1023px):** Collapsible sidebar, 2-column grids reduce to single column for some cards
- **Mobile (<768px):** Hidden sidebar with hamburger menu, all grids stack to single column, horizontal scroll for wide tables with sticky first column