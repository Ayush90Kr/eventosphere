# Eventosphere — Event Management & Registration Website

A complete, responsive, zero-build-step event management website built with semantic HTML5, modern CSS3 (CSS Grid, Flexbox, and CSS Custom Properties), and vanilla ES6+ JavaScript.

## Features

- **Homepage (`index.html`)**:
  - Sticky 3-zone navigation bar with Eventosphere brand wordmark, navigation links (`Home`, `Events`, `Register`), dark/light theme toggle, and responsive mobile hamburger drawer.
  - Hero section with editorial typography, entrance animation, and call-to-action linking to the events catalog.
  - Featured & Upcoming Events grid displaying 8 curated events (featured events prioritized first).
  - Real-time search bar filtering by event title or venue, plus category filter buttons (`All`, `Technology`, `Music`, `Sports`, `Business`, `Art`) with active states and an empty-state reset view.
- **Event Details & Registration (`event.html`)**:
  - Dynamic event loading via URL query parameter (`event.html?id=1`), with a clear error state and return link for invalid IDs.
  - Live countdown timer (days, hours, minutes, seconds) to the event start date.
  - Full event metadata: admission price, live seats remaining, venue, and full description.
  - Client-side JavaScript form validation (name, email regex, international phone format, and event selection) with inline field-specific error messages that clear as the user types.
  - `localStorage` persistence for registrations, duplicate registration prevention (by email + event), and automatic seat count updates.
- **Dark / Light Mode**:
  - Persists user preference in `localStorage` (`vespera_theme`) with smooth 200–260ms transitions.

## Folder Structure

```text
/
├── index.html              # Homepage
├── event.html              # Event details & registration page
├── css/
│   └── styles.css          # Design system, themes, and responsive layout
├── js/
│   ├── data.js             # Sample dataset of 8 events
│   ├── app.js              # Homepage rendering, search, filter, and theme
│   ├── event.js            # Event details, countdown timer, and registration
│   └── validation.js       # Form validation & localStorage helpers
├── assets/
│   └── images/             # Local event photography
├── README.md
└── .gitignore
```

## Setup Instructions

No build step or package installation is required to run the site:

1. **Open directly**: Double-click `index.html` to open it in any modern browser.
2. **Or run a local static server**:
   ```bash
   npx serve .
   # or
   python3 -m http.server 3000
   ```

## Technologies Used

- **HTML5**: Semantic landmarks (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`), accessible labels, and ARIA attributes.
- **CSS3**: Custom properties (`:root` and `.dark`), CSS Grid, Flexbox, `clamp()` fluid typography, and `prefers-reduced-motion` support.
- **Vanilla JavaScript (ES6+)**: DOM manipulation, URLSearchParams, `localStorage`, and `setInterval` countdown timer.

## Git Initialization & Push

```bash
git init
git add .
git commit -m "Initial commit: Vespera Events website"
git branch -M main
git remote add origin https://github.com/<your-username>/vespera-events.git
git push -u origin main
```

## Deployment Instructions

### GitHub Pages
1. Push your repository to GitHub.
2. Go to **Settings > Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**.
4. Choose the `main` branch and `/ (root)` folder, then click **Save**.
5. Your site will be live at `https://<your-username>.github.io/vespera-events/`.

### Netlify
1. **Drag & Drop**: Go to [app.netlify.com/drop](https://app.netlify.com/drop) and drag your project folder onto the page.
2. **GitHub Import**: Click **Add new site > Import an existing project**, connect GitHub, select your repository, leave the build command blank, set publish directory to `.`, and click **Deploy site**.

### Vercel
1. Go to [vercel.com/new](https://vercel.com/new) and import your GitHub repository.
2. Select **Other** as the Framework Preset, leave the Build Command and Output Directory empty, and click **Deploy**.

## Pre-Submission Verification Checklist

- [ ] **Responsiveness**: Tested at `375px` (mobile), `768px` (tablet), and `1280px+` (desktop) with zero horizontal overflow.
- [ ] **Search & Filter**: Real-time search by title/venue and category buttons work together, including the empty state.
- [ ] **Validation**: Submitting empty or invalid fields shows inline red error messages and blocks submission; errors clear on input.
- [ ] **localStorage**: Registrations persist across page reloads, duplicate email+event submissions are blocked, and dark/light mode persists.
- [ ] **Live URL**: Deployed site loads all assets, styles, and scripts without console errors.
