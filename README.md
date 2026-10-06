# Adriana & Robert's wedding

A responsive, single-page wedding website for Adriana Ierullo and Robert Dworak at The Barn at Cave Springs on October 30, 2027. It is built with plain HTML, CSS, and JavaScript; there is no package installation or build step.

## Run locally

Open `index.html` in a browser, or serve this directory with a static web server:

```sh
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## Day-of features

- Burgundy day-of welcome page with venue and event schedule
- Guest-facing seating lookup using the 92-name guest list, with a per-browser meal preference form
- Full-bleed venue-photo backdrops and map directions
- A separate guest photo-sharing page, linked from the main navigation and photo gallery

The existing 92 guest names are preserved for seating search. The ceremony is scheduled for 4:00–4:30 PM and the reception for 4:30–11:30 PM. Seating assignments have not been provided yet; matching guests are told their table details will appear once the chart is finalized. Add confirmed guest-to-table pairs to the `seatingAssignments` object in `index.html`.

The guest list is included in the public page source. Meal choices are not pre-filled: guests can search their exact name and save or update a provisional meal preference. Those choices are stored only in that browser's local storage; they are not sent to the couple, synchronized to other devices, or protected from other people using the same browser. GitHub Pages is static hosting and has no shared database or guest authentication. To collect choices centrally or securely, connect an authenticated backend before relying on these selections for catering. Update the provisional meal categories in `mealOptions` in `index.html` to match the confirmed menu.

`photos.html` is the guest contribution page for a collaborative photo album. To activate its QR code, create a shared album that allows guest contributions and paste its public HTTPS link into `SHARED_ALBUM_URL` near the bottom of `photos.html`. The page intentionally shows a setup message instead of a QR code until a real link is configured. QR generation uses QRCode.js from a CDN, so the photo page needs an internet connection.

Venue photos are embedded from the official [Vintage Hotels Cave Spring Vineyard page](https://www.vintage-hotels.com/cave-spring-vineyard/) and attributed on the site to Vintage Hotels and the photographers credited there (Afterglow Photography, Geoff Shaw Photography, and Loverly Photography). The page hotlinks those images rather than storing copies in this repository. Photos and display fonts require an internet connection.
