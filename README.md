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
- Guest-facing seating lookup using the 92-name guest list, with a read-only meal choice for exact-name matches
- Dedicated responsive Seating Plan diagram focused on table and bar locations
- Full-bleed venue-photo backdrops and map directions
- A separate guest photo-sharing page, linked from the main navigation and photo gallery

The existing 92 guest names are preserved for seating search. The ceremony is scheduled for 4:00–4:30 PM and the reception for 4:30–11:30 PM. Seating assignments have not been provided yet; matching guests are told their table details will appear once the chart is finalized. Add confirmed guest-to-table pairs to the `seatingAssignments` object in `index.html`.

The guest list and couple-entered meal choices are included in the public page source. Guests cannot edit meal choices. After receiving an RSVP, update the `mealChoices` object in `index.html` using the guest's exact listed name as the key and the confirmed meal choice as the value, then republish the site. Leave guests out of the object until their choice is confirmed; the lookup shows “Meal choice will appear here after your RSVP is received” otherwise. Meal choices are shown in the page UI only after an exact full-name search, but this static site does not provide authentication and its public source remains inspectable. GitHub Pages has no shared database or guest authentication.

`seating-plan.html` shows a custom, responsive autumn-colored diagram based on the supplied venue plan, with upholstered-chair illustrations, linen-style tabletops, and small fall centerpieces. It keeps the table arrangement and bar location while omitting the other rooms: six 72-inch rounds (up to 12 guests each), two 60-inch rounds (up to 8 each), and one six-foot table with two seats, for a maximum of 90. This is a capacity reference, not the couple's final assignments. Guests can use the main page's exact-name lookup for their personal assignment while the couple finalizes the chart.

`photos.html` is the guest contribution page for a collaborative photo album. To activate its QR code, create a shared album that allows guest contributions and paste its public HTTPS link into `SHARED_ALBUM_URL` near the bottom of `photos.html`. The page intentionally shows a setup message instead of a QR code until a real link is configured. QR generation uses QRCode.js from a CDN, so the photo page needs an internet connection.

Venue photos are embedded from the official [Vintage Hotels Cave Spring Vineyard page](https://www.vintage-hotels.com/cave-spring-vineyard/) and attributed on the site to Vintage Hotels and the photographers credited there (Afterglow Photography, Geoff Shaw Photography, and Loverly Photography). The page hotlinks those images rather than storing copies in this repository. Photos and display fonts require an internet connection.
