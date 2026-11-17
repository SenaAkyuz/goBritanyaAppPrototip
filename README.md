# GoBritanya — Student App Prototype

Clickable mobile prototype of a student app for [GoBritanya](https://www.gobritanya.com) residents.
Single HTML file, no build step and no dependencies.

**Run it:** open `index.html` in a browser (keep the `images/` folder next to it), or enable GitHub Pages for this repo.
On desktop it renders inside a phone frame; on a phone it runs full screen.

## Screens
- **Home** — check-in countdown, quick actions, resident perks, The Common Room, blog articles
- **My stay** — residence photo, check-in/out, arrival checklist, *Request an extension*
- **Request an extension** — weeks + note → confirmation, assigned to the city team
- **Support** — 24h emergency line, contacts, support requests, my requests, FAQ
- **Residences** — all 34 residences with photos, filters and detail pages
- EN / TR language switch

## Structure
- `index.html` — all CSS, JS and content. Editable content lives at the top of the script in `APP_DATA`.
- `images/residences/` — one building/common-area photo (`<id>.jpg`) and, where available, one room photo (`<id>-room.jpg`) per residence, taken from gobritanya.com (17 Nov 2026).

## Requests data model
Every request the student sends (extension, support, arrival time, residence enquiry) is created by `createRequest()` and stored in one list (`state.requests`, persisted to `localStorage`). Each item has `id`, `type`, `status` (`new` → `in_review` → `resolved`), `student`, `residence`, `assignedTo.team`, `details` and an `integration.hubspot` block — ready to be sent to a management portal / HubSpot tickets later. The JSON is visible on each request's detail screen.

Content source: gobritanya.com, captured 17 November 2026.
