# To The Music — Website Expansion Design
**Date:** 2026-03-15

## Overview

Expand the existing single-page festival website with new sections and updated content to reflect confirmed event details, instructor names, ticketing via Ticket Tailor, housing coordination, a venue map, merch, Instagram feed, and contact info.

---

## Updated Page Structure & Nav Order

About → Teachers → Schedule → Tickets → Housing → Map → Merch → Instagram → Contact

---

## Section Designs

### 1. About (expand existing)
- Keep the existing 6 feature cards
- Add two new subsections below the cards:
  - **"The Parties"** — paragraph explaining collaborative party curation with local NYC club/party organizers and promoters. Party lineups TBA closer to the month of the festival.

---

### 2. Teachers (new section)
- 4 cards: **Kenji, Jeff Selby, Melina, Miss Bibi**
- Each card: name, "Coming Soon" badge (photo/bio placeholder), days they teach (pulled from schedule)
- Match existing card visual style (dark bg, accent border on hover)

---

### 3. Schedule (update existing)

**May 13 changes:**
- Remove "Guest Arrivals" card
- Rename "Welcome Happy Hour + Festival Check-In" → "Dinner + Festival Check-In" (5:30–8:30 PM, Em Vietnamese Bistro)
- Rename "Welcome Party" → "Soul Records Laboratory" (8:00 PM–12:00 AM, Time Out Market BK)

**May 14 changes:**
- Update "Outdoor Potluck + Session" → "Picnic + Outdoor Session" (12:30–4:00 PM)
- Merge Q&A + Party 2 → "Q&A with Jeff Selby + Afterparty" (7:00 PM until late)

**May 15 changes:**
- Remove "Community Organizers Workshop"
- Replace generic workshop names with named instructors + venue (El Santo, Bushwick):
  - Workshop with Kenji — 12:00–1:30 PM
  - Workshop with Jeff Selby — 3:00–5:00 PM
  - Workshop with Melina — 5:30–7:00 PM
  - "Flower" Styling Workshop with Miss Bibi — 7:00–9:00 PM
- Rename "Party 3" → "House of Vibes with Jihad Muhammad" (10:00 PM until late, location TBD)

**May 16 changes:**
- Remove "Workshop 4: Follower Styling"
- Add NYC Dance Parade (10:00 AM call time, danceparade.org) — Jeff Selby is 2026 Grand Marshal
- Rename "Day Party 4" → "Love City NYC (Official Afterparty)" (2:00–10:00 PM, Crossroads Cafe, Bushwick)
- Remove "Open Evening"

**May 17 changes:**
- Replace generic workshop names with instructors + venue (Modega, Long Island City):
  - Workshop with Kenji — 12:00–2:00 PM
  - Workshop with Melina — 2:15–4:15 PM
  - Workshop with Miss Bibi — 4:30–6:30 PM
- Add venue "Modega, Long Island City" to battle card
- Add note: battle entry limited to festival participants

---

### 4. Tickets (update existing)
- Change all "Coming in March" button labels → "Get Tickets"
- All ticket buttons link to Ticket Tailor (URL to be filled in when ready — use `#` placeholder)
- Add note that individual workshop registration is also via Ticket Tailor

---

### 5. Housing Coordination (new section)
- Short intro paragraph: Reina coordinates housing for festival attendees
- Single CTA button: "Request Housing Coordination" → opens Google Form in new tab (URL placeholder)
- Simple centered layout, no form embedded on page

---

### 6. Map of Locations (new section)
- Embedded Google Maps iframe
- Pins for:
  - Time Out Market BK (May 13 — Soul Records Laboratory)
  - Location TBD for Picnic (May 14)
  - El Santo, Bushwick (May 15 — all workshops)
  - Crossroads Cafe, Bushwick (May 16 — Love City NYC afterparty)
  - NYC Dance Parade route/start (May 16)
  - Modega, Long Island City (May 17 — all workshops + battle)
- Note: May 14 potluck location TBD, omit pin until confirmed

---

### 7. Merch (new section)
- Two product rows using existing presale images from `assets/merch/`:
  - **T-Shirts** (`tshirts.PNG`) — $20, Comfort Colors heavyweight cotton, S–XL, 3 colors
  - **Sweat Towels** (`sweat_towels.PNG`) — $5 with t-shirt purchase, 100% cotton terry cloth, 3 colors
- CTA button: "Order Merch" → Ticket Tailor (URL placeholder, Google Sheet fallback)

---

### 8. Instagram (new section)
- Behold.so widget embed for `@tothemusicnyc`
- Section header with handle displayed and a "Follow Us" link to Instagram profile
- Behold embed URL/script to be added once account connected (placeholder div in HTML)

---

### 9. Contact (new section)
- Email address (placeholder to be filled in)
- Instagram: @tothemusicnyc (linked)
- Note directing housing questions to the housing coordination form

---

## Technical Decisions

- **All changes in `index.html`** — no new files, no build tools
- **Ticket Tailor** for ticketing and merch orders — use `#` placeholders until URLs are ready
- **Housing form** — Google Form opened in new tab via button (not embedded iframe)
- **Instagram feed** — Behold.so widget (free tier, 1 widget, auto-refreshing)
- **Map** — Google Maps embed iframe with multiple location pins via a custom map URL

---

## Placeholders / Content Needed Later
- Ticket Tailor URLs (tickets + merch)
- Google Form URL (housing)
- Teacher bios and photos
- Party organizer details (announced closer to the festival)
- Hotel/housing recommendations
- Contact email address
- May 14 potluck location
- Behold.so embed code (after connecting @tothemusicnyc)
