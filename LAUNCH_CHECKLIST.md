# To The Music — Pre-Launch Checklist

## How to use
Check off each item as it's completed. For items needing a URL or embed code, paste it in the notes field, then update `index.html`.

---

## 🔴 Blocking — Required Before Launch

### Ticketing
- [ ] **Ticket Tailor — Get Tickets buttons**
  - Create event on Ticket Tailor and copy the event URL
  - Update `href="#"` on all 3 ticket card buttons in `index.html` (search for `ticket-btn`)
  - _URL:_ _______________

- [ ] **Ticket Tailor — Order Merch button**
  - Add merch as a product in Ticket Tailor (or set up Google Sheet as fallback)
  - Update `href="#"` on the "Order Merch" button in the `#merch` section
  - _URL:_ _______________

### Dancers List
- [ ] **Set up the Dancers List for party discounts**
  - Decide on the mechanism: Google Form, Google Sheet signup, or Ticket Tailor registration
  - Determine what qualifies someone for the list (e.g. all-access pass holders, specific registration)
  - Update the "Dancers List" badge descriptions in the schedule event cards — currently says "Discounted entry via Dancers List" with no link or instructions
  - Add signup link/instructions to the relevant event cards in `index.html` (search for `Dancers List`)
  - Consider whether to add a dedicated section or FAQ entry explaining how the Dancers List works
  - _Signup URL/mechanism:_ _______________

### Housing
- [ ] **Google Form — Housing Coordination**
  - Reina creates the Google Form (name, email, brief note fields)
  - Update `href="#"` on the "Request Housing Coordination" button in the `#housing` section
  - _URL:_ _______________

### Instagram Feed
- [ ] **Behold.so — Instagram embed**
  - Create free account at [behold.so](https://behold.so)
  - Connect @tothemusicnyc Instagram account
  - Copy the embed snippet
  - In `index.html`, replace the `<div class="ig-placeholder">...</div>` block with the Behold embed code
  - _Behold widget ID:_ _______________

### Contact
- [ ] **Confirm contact email address**
  - Currently set to `hello@tothemusicnyc.com` — confirm this is correct or update in the `#contact` section
  - _Confirmed email:_ _______________

---

## 🟡 Nice to Have Before Launch

### Map
- [x] **Google My Maps — custom venue pins**
  - Embed URL: `https://www.google.com/maps/d/embed?mid=1qcN8Wg6fLk81OmWGx8F-QeE_LjnkfE4`

### Social Media
- [ ] **Update Instagram link in footer/nav**
  - Search `instagram.com/tothemusicnyc` in `index.html` — confirm all links are correct
- [ ] **Add Facebook/YouTube links** (if applicable)
  - Currently no Facebook or YouTube links on the site — add to footer if needed

---

## 🟢 Content — Fill In When Ready

### Teachers
- [ ] **Kenji** — photo + bio
- [ ] **Jeff Selby** — photo + bio
- [ ] **Melina** — photo + bio
- [ ] **Miss Bibi** — photo + bio
  - When ready: replace `<div class="teacher-photo-placeholder">` with `<img>` tag
  - Replace `<p class="teacher-bio-placeholder">Bio coming soon</p>` with actual bio

### Schedule — Venue TBDs
- [ ] **May 14 — Picnic + Outdoor Session** venue confirmed
  - Update "Location TBD" in `#day-thu` event card
  - _Venue:_ _______________
- [ ] **May 15 — House of Vibes with Jihad Muhammad** venue confirmed
  - Update "Location TBD" in `#day-fri` event card
  - _Venue:_ _______________

### Schedule — Workshop Details
- [ ] Workshop topics/descriptions filled in (currently "Details TBA" on all)
  - May 15: Kenji, Jeff Selby, Melina, Miss Bibi
  - May 17: Kenji, Melina, Miss Bibi

### Parties
- [ ] **Party organizer details announced**
  - Update the "The Parties" paragraph in the `#about` section with confirmed organizers/lineups

### FAQ
- [ ] **Review FAQ answers** for anything referencing "March" or other outdated info
  - Search `index.html` for "March" and update any stale references

---

## ✅ Complete

- [x] Nav links updated (About, Teachers, Schedule, Tickets, Housing, Venues, Merch, Instagram, Contact)
- [x] About section — 6 feature cards + party curation description
- [x] Teachers section — 4 Coming Soon cards
- [x] Schedule — all 5 days with real instructor names and venues
- [x] Tickets — "Get Tickets" buttons + Ticket Tailor note
- [x] Housing Coordination section — Reina description + CTA button
- [x] Venues Map section — 4 venue pills + Google Maps embed
- [x] Merch section — T-shirts ($20) + Sweat Towels ($5) with presale images
- [x] Instagram section — Behold.so placeholder
- [x] Contact section — email, Instagram, housing link
- [x] Mobile responsive design
- [x] FAQ accordion
- [x] Code of Conduct
