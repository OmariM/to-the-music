# To The Music — Festival Website

## Project Overview

Promotional website for the **To The Music NewStyle Hustle dance festival**, May 13-17, 2026.

**Tech stack:** Pure HTML/CSS/JS — single `index.html`, no frameworks, no build tools.
**Fonts:** Google Fonts (Poppins body, Playfair Display headings)

---

## File Structure

```
index.html                          — entire website (~1,500+ lines)
assets/
  to-the-music-logo.jpg             — festival logo
  schedule/
    may13-14.PNG                    — schedule reference images
    may15.PNG / mqy15.PNG           — (mqy15 is a duplicate/typo of may15)
    may16.PNG
    may17.PNG
  merch/
    tshirts.PNG                     — presale t-shirt image (used in Merch section)
    sweat_towels.PNG                — presale sweat towel image (used in Merch section)
to-the-music-prototype.mov          — demo video (61MB, not embedded)
deliverables/
  Ticketing-Platform-Proposal.docx  — proposal document
docs/plans/
  2026-03-15-website-expansion-design.md  — design doc
  2026-03-15-website-expansion.md         — implementation plan
CLAUDE.md                           — this file
```

---

## Design System

| Token | Value | Use |
|-------|-------|-----|
| Primary | `#e94560` | Red/pink accent |
| Secondary | `#16c79a` | Teal |
| Gold | `#f5a623` | Highlights |
| BG Dark | `#0a0a0f` | Page background |
| BG Card | `#111118` | Cards |
| BG Raised | `#1a1a25` | Elevated surfaces |
| Text | `#e8e8ef` | Body text |
| Text Muted | `#8888a0` | Secondary text |
| Text Dim | `#555570` | Tertiary text |

---

## Festival Content

**Dates:** May 13–17, 2026 (Wed–Sun)

| Day | Theme | Key Events |
|-----|-------|------------|
| Wed 5/13 | Welcome Events | Dinner + Festival Check-In (Em Vietnamese Bistro), Soul Records Laboratory (Time Out Market BK) |
| Thu 5/14 | Community Day | Picnic + Outdoor Session, Q&A with Jeff Selby + Afterparty |
| Fri 5/15 | Training Begins | Workshops: Kenji, Jeff Selby, Melina, Miss Bibi (El Santo, Bushwick); House of Vibes w/ Jihad Muhammad |
| Sat 5/16 | 12 Hrs to Party | NYC Dance Parade (Jeff Selby Grand Marshal), Love City NYC Afterparty (Crossroads Cafe, Bushwick) |
| Sun 5/17 | Train to Battle | Workshops: Kenji, Melina, Miss Bibi (Modega, LIC); HNT N'Tussle Battle |

**Ticket Tiers:**
- Single Day Pass: $65/day
- All Access Pass: $199 (featured)
- Parties Only: $85
- Individual Workshops: $35–$40
- Q&A (Jeff Selby): $20

---

## Feature Status

### ✅ Complete
- Full responsive layout (mobile, tablet, desktop)
- Hero section with animated logo and countdown timer
- About section (6 feature cards + party curation description)
- Teachers section (4 cards: Kenji, Jeff Selby, Melina, Miss Bibi — Coming Soon bios)
- 5-day schedule with real instructor names, venues, correct event details
- Schedule tab navigation, event filtering, expandable event cards
- 3-tier ticket pricing display with "Get Tickets" buttons + Ticket Tailor note
- FAQ accordion (7 items)
- Code of Conduct section
- Housing Coordination section (Reina, Google Form CTA — URL placeholder)
- Venues Map section (4 venue pills + embedded Google Maps)
- Merch section (T-shirts $20, Sweat Towels $5 — using presale images)
- Instagram section (Behold.so placeholder for @tothemusicnyc)
- Contact section (email, Instagram, housing link)
- Mobile hamburger menu
- Smooth scroll, hover animations, transitions throughout

### 🔴 Needs Live URLs (placeholders in place)
- Ticket Tailor URLs — ticket buttons and "Order Merch" button all link to `#`
- Google Form URL — Housing "Request Housing Coordination" button links to `#`
- Behold.so embed — Instagram section shows placeholder; connect @tothemusicnyc at behold.so
- Google My Maps — Map iframe uses generic Brooklyn embed; replace with custom multi-pin map
- Contact email — currently `hello@tothemusicnyc.com`, confirm correct address

### 🟡 Incomplete Content
- Teacher bios and photos — all 4 teachers show "Bio coming soon"
- Party organizer details — announced closer to festival month
- May 14 potluck location — listed as "Location TBD"
- May 15 House of Vibes venue — listed as "Location TBD"

---

## Development Notes

- All edits go in `index.html` unless there's a clear reason to split files
- No build step — changes are immediately reflected in the browser
- JS is inline at the bottom of `index.html` (~90 lines)
- CSS is inline in a `<style>` block in `<head>`
