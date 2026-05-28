# AGENTS.md — Hotel SRP Shirdi

## Project Architecture

This is a zero-dependency static HTML site. All markup, styles, and JavaScript live in a single file:

```
index.html        # complete site — HTML + embedded CSS + inline JS
README.md         # user-facing setup guide
AGENTS.md         # this file
```

No build pipeline, no framework, no node_modules needed for the site itself.

## Coding Conventions

- **CSS variables**: All brand colours are defined in `:root` at the top of the `<style>` block. Always reference variables rather than hard-coding hex values.
- **Fonts**: `Cormorant Garamond` (serif, display/headings) and `DM Sans` (sans-serif, body). Loaded via Google Fonts in `<head>`.
- **Scroll reveal**: Elements with `.reveal` class are faded-in by `IntersectionObserver` in the inline `<script>`. Stagger via `.reveal-delay-1` through `.reveal-delay-5`.
- **Responsive**: Breakpoints at `900px` (two-column layout collapses) and `700px` (mobile padding/nav). No CSS framework.
- **WhatsApp links**: Follow `https://wa.me/<countrycode><number>?text=<urlencoded>` format. Currently use the placeholder `919876543210`.

## Non-Obvious Decisions

- The hero background is CSS `background` shorthand on `.hero-bg` (a separate `div`) so that it can be animated independently via `transform: scale(...)` without causing a page reflow on the content above.
- The diagonal white "cut" at the bottom of the hero is achieved with `clip-path: polygon(...)` on the `::after` pseudo-element of `.hero`, not a separate element, to keep the DOM minimal.
- Images use `loading="lazy"` to defer off-screen room photos.
- The `<iframe>` Google Maps embed uses `referrerpolicy="no-referrer-when-downgrade"` to avoid console warnings on modern browsers.

## What to Update Before Going Live

1. Replace all instances of `919876543210` with the real WhatsApp/phone number.
2. Swap Unsplash placeholder image URLs with actual hotel room photos.
3. Replace the hero `url(...)` in `.hero-bg` CSS with a real hotel exterior image.
4. Update the Google Maps `src` with a precise embed URL for the hotel's verified Maps listing.
