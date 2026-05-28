# Hotel SRP Shirdi — Website

A single-page hotel landing site for Hotel SRP Shirdi, located near the Shirdi Sai Baba Temple in Maharashtra, India.

## Key Technologies

- Pure HTML5 / CSS3 / vanilla JS — no framework dependencies
- Google Fonts (`Cormorant Garamond` + `DM Sans`)
- Unsplash CDN for room placeholder images
- Google Maps embed for location
- WhatsApp deep-link CTAs (`wa.me`) for instant booking

## How to Run Locally

Open `index.html` directly in any browser, or serve with any static file server:

```bash
npx serve .
# then open http://localhost:3000
```

No build step required.

## Customisation

- **Phone number**: Replace `919876543210` globally in `index.html` with the hotel's real WhatsApp number (country code + number, no spaces or `+`).
- **Room images**: Replace the Unsplash `src` URLs on the `<img>` tags with actual room photos.
- **Hero image**: Replace the `url(...)` in `.hero-bg` CSS with a real hotel/exterior photo.
- **Map**: The Google Maps iframe `src` can be updated to a precise `place_id` embed URL once the hotel is listed on Google Maps.
