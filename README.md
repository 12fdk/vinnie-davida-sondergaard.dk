# Vinnie Davida Søndergaard

The **production marketing site** for Vinnie Davida Søndergaard — a static site
(Danish, `da_DK`) hosted on **GitHub Pages**. No build step, no framework: plain
HTML, one shared stylesheet, and a handful of small progressive-enhancement
scripts.

**Live URL:** https://vinnie-davida-sondergaard.dk

## The three focuses

The site presents three distinct areas, each with its own tone:

- **Klinik** — Fysiurgisk massage; calm/clinical, leads to booking & calendar.
- **Workout** — Outdoor training (e.g. TRX); energetic, with signup.
- **People & Performance** — B2B professional services; polished and premium.

## What's live vs. what isn't

There is no backend or server. Most of the site is content, but two things are
worth knowing before you trust a form on it:

**Working:**

- **Klinik booking** is real. The "Book tid" buttons point at a live
  [EZME](https://ezme.io/c/Tf/eSrT) calendar.
  `assets/js/booking-modal.js` opens it in an on-page lightbox; without JS the
  links simply open EZME in a new tab.
- **Contact** happens via `mailto:vinnie@davida-sondergaard.dk` links, present
  in the footer of every page.

> **⚠️ Not working — these capture no leads:**
>
> - The **Workout signup form** (`assets/js/signup.js`) does not submit
>   anywhere. Clicking submit just swaps the form for a static confirmation
>   panel.
> - The **People & Performance contact/lead form** (`assets/js/contact.js`) does
>   the same.
>
> Anyone who fills these in believes they have been signed up or contacted, and
> nothing reaches Vinnie. They need a real submission target (form service or
> mail relay) before they can be relied on.

**Limitation:** the cookie banner (`assets/js/cookie.js`) records the visitor's
choice in local storage but does not load or block any actual cookies.

## Local preview

This is a static site — serve it from the repo root:

```bash
python3 -m http.server 8765
```

Then open:

- Landing: http://localhost:8765/
- Om: http://localhost:8765/om/
- Klinik: http://localhost:8765/klinik/
- Workout: http://localhost:8765/workout/
- People & Performance: http://localhost:8765/people-performance/

If port 8765 is busy, free it (`pkill -f "http.server 8765"`) or pick another
port.

## Project structure

```
index.html                     Landing page
om/index.html                  About page
klinik/index.html              Klinik sub-site (EZME booking)
workout/index.html             Workout sub-site (signup mock)
people-performance/index.html  People & Performance sub-site (contact mock)
privatlivspolitik.html         Privacy policy
cookie-politik.html            Cookie policy
404.html                       Custom not-found page (served by GitHub Pages)
assets/css/tokens.css          Shared design tokens (colors, type, spacing)
assets/js/nav.js               Shared top-nav / mobile menu + footer year
assets/js/reveal.js            Scroll-reveal animations
assets/js/booking-modal.js     Klinik EZME booking lightbox
assets/js/signup.js            Workout signup form mock
assets/js/contact.js           People & Performance contact form mock
assets/js/cookie.js            Cookie consent banner
assets/images/                 Optimised .webp page images
assets/images/source/          Source media (logos, photos, references)
assets/originals/              Unprocessed original photography
design.md                      Design source of truth
```

## Design reference

[`design.md`](design.md) is the **design source of truth** — brand, color
palette, typography, content/copy, and the catalogue of reusable media assets.
Read and follow it when changing anything visual.

## Credits & copyright

Content and media are © Vinnie Davida Søndergaard and the respective
photographers (e.g. Martin Kaufmann) and partners whose logos appear here, used
with permission. The original design is credited to Standoutmedia.
