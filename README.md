# Nishi Singh — Personal CV Website

A modern, multi-page personal site featuring your CV. Built with vanilla HTML, CSS, and a touch of JS — no build step, no dependencies.

## Files

```
cv-site/
├── index.html      → Home (hero, stats, featured engagements, sectors)
├── about.html      → Bio, work history (timeline), skills, education
├── projects.html   → Featured engagement (Sizewell C) + 10-engagement list
├── contact.html    → Email, phone, LinkedIn, contact form, FAQ
├── styles.css      → Shared stylesheet (all pages)
└── README.md       → This file
```

## Run locally

Simplest: open `index.html` in your browser.

For cleaner local routing:

```bash
# Python
python3 -m http.server 8000

# Or Node
npx serve .
```

Then visit `http://localhost:8000`.

## Deploy (free options)

- **GitHub Pages** — push the folder to a repo, enable Pages in settings.
- **Netlify** — drag-and-drop the folder onto [netlify.com/drop](https://app.netlify.com/drop).
- **Vercel** — `vercel deploy` from the folder.
- **Cloudflare Pages** — connect a Git repo or upload directly.

If you'd like a custom domain (e.g. `nishisingh.com`), all four providers support that for free — you just point your domain's DNS at them.

## What's on each page

**Home** — Hero with your name, "snapshot" terminal panel, four stats (9+ years, 4 sectors, £3M+ pipeline, 40% cycle reduction), scrolling skills marquee, four featured engagements, and a "sectors" grid.

**About** — Four-paragraph bio, profile card with metadata, full work timeline (Capgemini Invent → Capgemini Mumbai → J&J → JCPenney → SPAR → Spencer's), four-category skills grid, and four education cards.

**Engagements** — Sizewell C as featured engagement, then 10 case studies covering Capgemini, J&J, JCPenney, and Spencer's work.

**Contact** — Email, phone, LinkedIn, location, live London clock, working contact form (opens user's email client), and a 4-question FAQ.

## Customizing

All your details from the CV are already in place. If anything changes, the items most likely to need updates:

- **Stats on home page** (`index.html`, `<div class="stats">`) — pick the four numbers that best represent your story
- **Profile photo** — currently a stylized "N" letter. To use a real photo, edit `about.html` and replace `<div class="profile-photo">N</div>` with `<img src="your-photo.jpg" class="profile-photo">`
- **Footer** — same text appears on all four pages; update once per file if needed
- **Status indicator** — change "Open to opportunities" in the nav and footer when needed

## Theming

All colors and fonts are CSS variables at the top of `styles.css`:

```css
:root {
  --accent: #D4FF3A;     /* electric chartreuse — main accent */
  --accent-2: #FF5722;   /* warm orange — secondary */
  --bg: #0A0A0B;         /* near-black background */
  --text: #ECEAE3;       /* warm off-white */
  --serif: 'Fraunces', serif;
  --sans: 'Onest', sans-serif;
  --mono: 'JetBrains Mono', monospace;
}
```

Want a light theme? Swap `--bg` to a near-white and `--text` to dark. The whole site retones with one variable.

## Notes

- Contact form opens the user's email client via `mailto:` — no backend needed. To use a real form (so messages don't depend on the sender's email setup), swap in [Formspree](https://formspree.io), [Web3Forms](https://web3forms.com), or your own endpoint.
- The site is fully responsive and works on mobile.
- Fonts are loaded from Google Fonts; for production you may want to self-host them.
- The live London clock on the contact page updates every second.
