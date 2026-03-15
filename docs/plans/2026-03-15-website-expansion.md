# Website Expansion Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Expand the To The Music festival website with 6 new sections (Teachers, Housing, Map, Merch, Instagram, Contact), update the About section, fix the Schedule with real instructor names and venues, and update Tickets to reference Ticket Tailor.

**Architecture:** All changes happen inside the single `index.html` file. CSS is in the `<style>` block in `<head>`. JS is inline at the bottom. New sections follow the existing pattern: a `<section id="...">` with matching nav link. No build tools, no frameworks.

**Tech Stack:** Pure HTML5, CSS3, vanilla JS. Google Fonts already loaded. Behold.so for Instagram embed (script tag). Google Maps iframe for venue map.

---

## Reference: Existing Design System

Colors (CSS variables already defined):
- `--accent: #e94560` (red/pink)
- `--secondary: #16c79a` (teal)
- `--gold: #f5a623`
- `--bg-dark: #0a0a0f`
- `--bg-card: #111118`
- `--bg-raised: #1a1a25`
- `--text: #e8e8ef`
- `--text-muted: #8888a0`
- `--text-dim: #555570`

Existing section pattern:
```html
<section id="sectionname">
  <div class="container">
    <div class="section-header">
      <h2>Section Title</h2>
      <p class="section-sub">Subtitle text</p>
    </div>
    <!-- content -->
  </div>
</section>
```

Existing card pattern:
```html
<div class="card">
  <!-- content -->
</div>
```

---

## Task 1: Update Nav Links

**Files:**
- Modify: `index.html` — nav `<ul>` (around line 464–470) and footer nav (around line 1111)

**Step 1: Update the main nav**

Replace the existing nav `<ul>` links with:
```html
<li><a href="#about">About</a></li>
<li><a href="#teachers">Teachers</a></li>
<li><a href="#schedule">Schedule</a></li>
<li><a href="#tickets">Tickets</a></li>
<li><a href="#housing">Housing</a></li>
<li><a href="#map">Venues</a></li>
<li><a href="#merch">Merch</a></li>
<li><a href="#instagram">Instagram</a></li>
<li><a href="#contact">Contact</a></li>
```

**Step 2: Update the footer nav** to match the same links.

**Step 3: Verify** — open in browser, confirm all nav links scroll to correct sections (existing ones still work).

**Step 4: Commit**
```bash
git add index.html
git commit -m "feat: update nav with all new section links"
```

---

## Task 2: Update About Section — Add Party Description

**Files:**
- Modify: `index.html` — `<section id="about">`, after the existing 6-card grid

**Step 1: Add the party subsection** directly after the closing `</div>` of the about cards grid:

```html
<div class="about-parties">
  <h3>The Parties</h3>
  <p>Every night at To The Music ends on the dance floor. We're collaborating with local NYC club organizers, party promoters, and tastemakers to curate nights that feel at home in the city's dance music scene — not just a festival afterthought. Each party is designed to blend the hustle community with the energy of NYC nightlife.</p>
  <p class="about-parties-note">Party lineups and venues are announced closer to the month of the festival. Follow <a href="https://instagram.com/tothemusicnyc" target="_blank">@tothemusicnyc</a> for updates.</p>
</div>
```

**Step 2: Add CSS** for `.about-parties` in the `<style>` block (after existing about styles):

```css
.about-parties {
  max-width: 700px;
  margin: 3rem auto 0;
  text-align: center;
}
.about-parties h3 {
  font-family: 'Playfair Display', serif;
  font-size: 1.6rem;
  color: var(--text);
  margin-bottom: 1rem;
}
.about-parties p {
  color: var(--text-muted);
  line-height: 1.8;
  margin-bottom: 0.75rem;
}
.about-parties-note {
  font-size: 0.9rem;
  color: var(--text-dim);
}
.about-parties-note a {
  color: var(--accent);
  text-decoration: none;
}
.about-parties-note a:hover { text-decoration: underline; }
```

**Step 3: Verify** — About section shows 6 cards followed by party description paragraph.

**Step 4: Commit**
```bash
git commit -m "feat: add party description to about section"
```

---

## Task 3: Add Teachers Section

**Files:**
- Modify: `index.html` — insert new `<section id="teachers">` after the closing `</section>` of About

**Step 1: Add the section HTML** after About's closing `</section>`:

```html
<!-- ========== TEACHERS ========== -->
<section id="teachers">
  <div class="container">
    <div class="section-header">
      <h2>Meet the Teachers</h2>
      <p class="section-sub">World-class instructors bringing their expertise to New York City</p>
    </div>
    <div class="teachers-grid">

      <div class="teacher-card">
        <div class="teacher-photo-placeholder">
          <span>Kenji</span>
        </div>
        <div class="teacher-info">
          <h3 class="teacher-name">Kenji</h3>
          <div class="teacher-days">
            <span class="teacher-day">Fri May 15</span>
            <span class="teacher-day">Sun May 17</span>
          </div>
          <p class="teacher-bio-placeholder">Bio coming soon</p>
        </div>
      </div>

      <div class="teacher-card">
        <div class="teacher-photo-placeholder">
          <span>Jeff Selby</span>
        </div>
        <div class="teacher-info">
          <h3 class="teacher-name">Jeff Selby</h3>
          <div class="teacher-days">
            <span class="teacher-day">Thu May 14</span>
            <span class="teacher-day">Fri May 15</span>
          </div>
          <p class="teacher-bio-placeholder">Bio coming soon</p>
        </div>
      </div>

      <div class="teacher-card">
        <div class="teacher-photo-placeholder">
          <span>Melina</span>
        </div>
        <div class="teacher-info">
          <h3 class="teacher-name">Melina</h3>
          <div class="teacher-days">
            <span class="teacher-day">Fri May 15</span>
            <span class="teacher-day">Sun May 17</span>
          </div>
          <p class="teacher-bio-placeholder">Bio coming soon</p>
        </div>
      </div>

      <div class="teacher-card">
        <div class="teacher-photo-placeholder">
          <span>Miss Bibi</span>
        </div>
        <div class="teacher-info">
          <h3 class="teacher-name">Miss Bibi</h3>
          <div class="teacher-days">
            <span class="teacher-day">Fri May 15</span>
            <span class="teacher-day">Sun May 17</span>
          </div>
          <p class="teacher-bio-placeholder">Bio coming soon</p>
        </div>
      </div>

    </div>
  </div>
</section>
```

**Step 2: Add CSS** in the `<style>` block:

```css
#teachers { background: var(--bg-section); }
.teachers-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}
.teacher-card {
  background: var(--bg-card);
  border: 1px solid #2a2a3a;
  border-radius: 12px;
  overflow: hidden;
  transition: transform 0.3s, border-color 0.3s;
}
.teacher-card:hover {
  transform: translateY(-4px);
  border-color: var(--accent);
}
.teacher-photo-placeholder {
  width: 100%;
  aspect-ratio: 1;
  background: var(--bg-raised);
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Playfair Display', serif;
  font-size: 1.2rem;
  color: var(--text-dim);
  border-bottom: 1px solid #2a2a3a;
}
.teacher-info {
  padding: 1.25rem;
}
.teacher-name {
  font-family: 'Playfair Display', serif;
  font-size: 1.2rem;
  color: var(--text);
  margin-bottom: 0.5rem;
}
.teacher-days {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
  margin-bottom: 0.75rem;
}
.teacher-day {
  font-size: 0.7rem;
  background: rgba(233, 69, 96, 0.15);
  color: var(--accent);
  border: 1px solid rgba(233, 69, 96, 0.3);
  border-radius: 4px;
  padding: 0.2rem 0.5rem;
}
.teacher-bio-placeholder {
  font-size: 0.85rem;
  color: var(--text-dim);
  font-style: italic;
}
```

**Step 3: Verify** — Teachers section shows 4 cards with names, teaching days, and "Bio coming soon" placeholders.

**Step 4: Commit**
```bash
git commit -m "feat: add teachers section with coming-soon bios"
```

---

## Task 4: Update Schedule — May 13

**Files:**
- Modify: `index.html` — `<div class="schedule-day active" id="day-wed">` (around line 560)

**Step 1: Replace the entire contents of `#day-wed`** with:

```html
<div class="schedule-day active" id="day-wed">
  <div class="schedule-day-header">
    <h3>Wednesday, May 13</h3>
    <span class="day-badge">Welcome Events</span>
  </div>
  <div class="schedule-timeline">

    <div class="time-group">
      <div class="time-group-label">
        <div class="time-group-icon evening">&#127769;</div>
        <div class="time-group-text">Evening</div>
        <div class="time-group-line"></div>
      </div>
      <div class="evt-card" data-type="social">
        <div class="evt-top">
          <div class="evt-name">Dinner + Festival Check-In</div>
          <div class="evt-price free">FREE</div>
        </div>
        <div class="evt-bottom">
          <span class="evt-time"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg> 5:30 &ndash; 8:30 PM</span>
          <span class="evt-location">Em Vietnamese Bistro</span>
          <span class="evt-type social">Social</span>
        </div>
        <div class="evt-desc">Pick up your festival badge over dinner. A relaxed welcome to the week — meet your fellow dancers at Em Vietnamese Bistro before the night heats up.</div>
        <div class="evt-expand-hint">tap for details</div>
      </div>
    </div>

    <div class="time-group">
      <div class="time-group-label">
        <div class="time-group-icon latenight">&#10024;</div>
        <div class="time-group-text">Late Night</div>
        <div class="time-group-line"></div>
      </div>
      <div class="evt-card" data-type="party">
        <div class="evt-top">
          <div class="evt-name">Soul Records Laboratory</div>
          <div class="evt-price special">Dancers List</div>
        </div>
        <div class="evt-bottom">
          <span class="evt-time"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg> 8:00 PM &ndash; 12:00 AM</span>
          <span class="evt-location">Time Out Market BK</span>
          <span class="evt-type party">Party</span>
        </div>
        <div class="evt-desc">Kick off the festival with a vinyl-driven night at Time Out Market BK. Discounted entry through the Dancers List.</div>
        <div class="evt-expand-hint">tap for details</div>
      </div>
    </div>

  </div>
</div>
```

**Step 2: Add `.evt-location` CSS** in the style block (near other `.evt-` styles):

```css
.evt-location {
  font-size: 0.75rem;
  color: var(--secondary);
  display: flex;
  align-items: center;
  gap: 0.25rem;
}
```

**Step 3: Verify** — May 13 tab shows 2 events with correct names, times, and locations.

**Step 4: Commit**
```bash
git commit -m "fix: update May 13 schedule with correct event names and venues"
```

---

## Task 5: Update Schedule — May 14

**Files:**
- Modify: `index.html` — `<div class="schedule-day" id="day-thu">` (around line 628)

**Step 1: Replace `#day-thu` contents** with:

```html
<div class="schedule-day" id="day-thu">
  <div class="schedule-day-header">
    <h3>Thursday, May 14</h3>
    <span class="day-badge">Community Day</span>
  </div>
  <div class="schedule-timeline">

    <div class="time-group">
      <div class="time-group-label">
        <div class="time-group-icon midday">&#9728;</div>
        <div class="time-group-text">Afternoon</div>
        <div class="time-group-line"></div>
      </div>
      <div class="evt-card" data-type="social">
        <div class="evt-top">
          <div class="evt-name">Picnic + Outdoor Session</div>
          <div class="evt-price paid">Free / $10</div>
        </div>
        <div class="evt-bottom">
          <span class="evt-time"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg> 12:30 &ndash; 4:00 PM</span>
          <span class="evt-location">Location TBD</span>
          <span class="evt-type social">Social</span>
        </div>
        <div class="evt-desc">Bring your own food and drinks for free entry, or drop in for $10. A relaxed outdoor afternoon to connect with the community over food and casual dancing.</div>
        <div class="evt-expand-hint">tap for details</div>
      </div>
    </div>

    <div class="time-group">
      <div class="time-group-label">
        <div class="time-group-icon latenight">&#10024;</div>
        <div class="time-group-text">Evening</div>
        <div class="time-group-line"></div>
      </div>
      <div class="evt-card" data-type="community">
        <div class="evt-top">
          <div class="evt-name">Q&amp;A with Jeff Selby + Afterparty</div>
          <div class="evt-price paid">$20</div>
        </div>
        <div class="evt-bottom">
          <span class="evt-time"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg> 7:00 PM &ndash; Late</span>
          <span class="evt-location">Location TBD</span>
          <span class="evt-type community">Community</span>
        </div>
        <div class="evt-desc">An intimate evening discussion with NewStyle Hustle pioneer Jeff Selby. Ask questions, gain insight, and connect with the movement's roots — then dance it out at the afterparty. Limited spots available.</div>
        <div class="evt-expand-hint">tap for details</div>
      </div>
    </div>

  </div>
</div>
```

**Step 2: Verify** — May 14 tab shows 2 events correctly.

**Step 3: Commit**
```bash
git commit -m "fix: update May 14 schedule"
```

---

## Task 6: Update Schedule — May 15

**Files:**
- Modify: `index.html` — `<div class="schedule-day" id="day-fri">` (around line 697)

**Step 1: Replace `#day-fri` contents** with:

```html
<div class="schedule-day" id="day-fri">
  <div class="schedule-day-header">
    <h3>Friday, May 15</h3>
    <span class="day-badge">Training Begins</span>
  </div>
  <div class="schedule-timeline">

    <div class="time-group">
      <div class="time-group-label">
        <div class="time-group-icon midday">&#9728;</div>
        <div class="time-group-text">Mid-Day</div>
        <div class="time-group-line"></div>
      </div>
      <div class="evt-card" data-type="workshop">
        <div class="evt-top">
          <div class="evt-name">Workshop with Kenji</div>
          <div class="evt-price paid">$40</div>
        </div>
        <div class="evt-bottom">
          <span class="evt-time"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg> 12:00 &ndash; 1:30 PM</span>
          <span class="evt-location">El Santo, Bushwick</span>
          <span class="evt-type workshop">Workshop</span>
        </div>
        <div class="evt-desc">Opening workshop of the festival with Kenji. Details TBA.</div>
        <div class="evt-expand-hint">tap for details</div>
      </div>
    </div>

    <div class="time-group">
      <div class="time-group-label">
        <div class="time-group-icon evening">&#127769;</div>
        <div class="time-group-text">Afternoon</div>
        <div class="time-group-line"></div>
      </div>
      <div class="evt-card" data-type="workshop">
        <div class="evt-top">
          <div class="evt-name">Workshop with Jeff Selby</div>
          <div class="evt-price paid">$40</div>
        </div>
        <div class="evt-bottom">
          <span class="evt-time"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg> 3:00 &ndash; 5:00 PM</span>
          <span class="evt-location">El Santo, Bushwick</span>
          <span class="evt-type workshop">Workshop</span>
        </div>
        <div class="evt-desc">Workshop with NewStyle Hustle pioneer Jeff Selby. Details TBA.</div>
        <div class="evt-expand-hint">tap for details</div>
      </div>
      <div class="evt-card" data-type="workshop">
        <div class="evt-top">
          <div class="evt-name">Workshop with Melina</div>
          <div class="evt-price paid">$35</div>
        </div>
        <div class="evt-bottom">
          <span class="evt-time"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg> 5:30 &ndash; 7:00 PM</span>
          <span class="evt-location">El Santo, Bushwick</span>
          <span class="evt-type workshop">Workshop</span>
        </div>
        <div class="evt-desc">Workshop with Melina. Details TBA.</div>
        <div class="evt-expand-hint">tap for details</div>
      </div>
      <div class="evt-card" data-type="workshop">
        <div class="evt-top">
          <div class="evt-name">"Flower" Styling Workshop with Miss Bibi</div>
          <div class="evt-price paid">$35</div>
        </div>
        <div class="evt-bottom">
          <span class="evt-time"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg> 7:00 &ndash; 9:00 PM</span>
          <span class="evt-location">El Santo, Bushwick</span>
          <span class="evt-type workshop">Workshop</span>
        </div>
        <div class="evt-desc">Miss Bibi's signature "Flower" styling workshop. Details TBA.</div>
        <div class="evt-expand-hint">tap for details</div>
      </div>
    </div>

    <div class="time-group">
      <div class="time-group-label">
        <div class="time-group-icon latenight">&#10024;</div>
        <div class="time-group-text">Late Night</div>
        <div class="time-group-line"></div>
      </div>
      <div class="evt-card" data-type="party">
        <div class="evt-top">
          <div class="evt-name">House of Vibes with Jihad Muhammad</div>
          <div class="evt-price special">Dancers List</div>
        </div>
        <div class="evt-bottom">
          <span class="evt-time"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg> 10:00 PM &ndash; Late</span>
          <span class="evt-location">Location TBD</span>
          <span class="evt-type party">Party</span>
        </div>
        <div class="evt-desc">Dance the night away after a full day of workshops. Jihad Muhammad on the decks. Discounted entry via Dancers List.</div>
        <div class="evt-expand-hint">tap for details</div>
      </div>
    </div>

  </div>
</div>
```

**Step 2: Verify** — May 15 tab shows 4 workshops with instructor names + locations, then late night party.

**Step 3: Commit**
```bash
git commit -m "fix: update May 15 schedule with instructor names and venues"
```

---

## Task 7: Update Schedule — May 16

**Files:**
- Modify: `index.html` — `<div class="schedule-day" id="day-sat">` (around line 793)

**Step 1: Replace `#day-sat` contents** with:

```html
<div class="schedule-day" id="day-sat">
  <div class="schedule-day-header">
    <h3>Saturday, May 16</h3>
    <span class="day-badge">12 Hrs to Party</span>
  </div>
  <div class="schedule-timeline">

    <div class="time-group">
      <div class="time-group-label">
        <div class="time-group-icon midday">&#9728;</div>
        <div class="time-group-text">Morning</div>
        <div class="time-group-line"></div>
      </div>
      <div class="evt-card" data-type="social">
        <div class="evt-top">
          <div class="evt-name">NYC Dance Parade</div>
          <div class="evt-price free">FREE</div>
        </div>
        <div class="evt-bottom">
          <span class="evt-time"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg> ~10:00 AM Call Time</span>
          <span class="evt-location"><a href="https://danceparade.org" target="_blank" style="color:var(--secondary);text-decoration:none;">danceparade.org</a></span>
          <span class="evt-type social">Social</span>
        </div>
        <div class="evt-desc">Join the NYC Dance Parade! Our very own Jeff Selby is the 2026 Grand Marshal. Details and parade route at danceparade.org.</div>
        <div class="evt-expand-hint">tap for details</div>
      </div>
    </div>

    <div class="time-group">
      <div class="time-group-label">
        <div class="time-group-icon evening">&#127769;</div>
        <div class="time-group-text">Afternoon</div>
        <div class="time-group-line"></div>
      </div>
      <div class="evt-card" data-type="party">
        <div class="evt-top">
          <div class="evt-name">Love City NYC — Official Afterparty</div>
          <div class="evt-price special">Dancers List</div>
        </div>
        <div class="evt-bottom">
          <span class="evt-time"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg> 2:00 &ndash; 10:00 PM</span>
          <span class="evt-location">Crossroads Cafe, Bushwick</span>
          <span class="evt-type party">Party</span>
        </div>
        <div class="evt-desc">The official Dance Parade afterparty. Afternoon into evening social dance vibes at Crossroads Cafe in Bushwick. Discounted entry via Dancers List.</div>
        <div class="evt-expand-hint">tap for details</div>
      </div>
    </div>

  </div>
</div>
```

**Step 2: Verify** — May 16 tab shows Dance Parade + Love City NYC afterparty.

**Step 3: Commit**
```bash
git commit -m "fix: update May 16 schedule with Dance Parade and Love City NYC"
```

---

## Task 8: Update Schedule — May 17

**Files:**
- Modify: `index.html` — `<div class="schedule-day" id="day-sun">` (around line 863)

**Step 1: Replace workshop cards in `#day-sun`** (keep battle card, just update the 3 workshop cards and add venue to battle):

Replace Workshop 5, 6, 7 cards and update battle card with:

```html
<div class="schedule-day" id="day-sun">
  <div class="schedule-day-header">
    <h3>Sunday, May 17</h3>
    <span class="day-badge">Train to Battle</span>
  </div>
  <div class="schedule-timeline">

    <div class="time-group">
      <div class="time-group-label">
        <div class="time-group-icon midday">&#9728;</div>
        <div class="time-group-text">Mid-Day</div>
        <div class="time-group-line"></div>
      </div>
      <div class="evt-card" data-type="workshop">
        <div class="evt-top">
          <div class="evt-name">Workshop with Kenji</div>
          <div class="evt-price paid">$40</div>
        </div>
        <div class="evt-bottom">
          <span class="evt-time"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg> 12:00 &ndash; 2:00 PM</span>
          <span class="evt-location">Modega, Long Island City</span>
          <span class="evt-type workshop">Workshop</span>
        </div>
        <div class="evt-desc">Final workshop with Kenji before the battle. Details TBA.</div>
        <div class="evt-expand-hint">tap for details</div>
      </div>
      <div class="evt-card" data-type="workshop">
        <div class="evt-top">
          <div class="evt-name">Workshop with Melina</div>
          <div class="evt-price paid">$35</div>
        </div>
        <div class="evt-bottom">
          <span class="evt-time"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg> 2:15 &ndash; 4:15 PM</span>
          <span class="evt-location">Modega, Long Island City</span>
          <span class="evt-type workshop">Workshop</span>
        </div>
        <div class="evt-desc">Afternoon intensive with Melina. Details TBA.</div>
        <div class="evt-expand-hint">tap for details</div>
      </div>
      <div class="evt-card" data-type="workshop">
        <div class="evt-top">
          <div class="evt-name">Workshop with Miss Bibi</div>
          <div class="evt-price paid">$35</div>
        </div>
        <div class="evt-bottom">
          <span class="evt-time"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg> 4:30 &ndash; 6:30 PM</span>
          <span class="evt-location">Modega, Long Island City</span>
          <span class="evt-type workshop">Workshop</span>
        </div>
        <div class="evt-desc">Final workshop of the festival with Miss Bibi before the battle begins. Details TBA.</div>
        <div class="evt-expand-hint">tap for details</div>
      </div>
    </div>

    <div class="time-group">
      <div class="time-group-label">
        <div class="time-group-icon latenight">&#10024;</div>
        <div class="time-group-text">Evening</div>
        <div class="time-group-line"></div>
      </div>
      <div class="evt-card" data-type="battle">
        <div class="evt-top">
          <div class="evt-name">NewStyle Hustle N' Tussle</div>
          <div class="evt-price paid">$25</div>
        </div>
        <div class="evt-bottom">
          <span class="evt-time"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg> 6:45 &ndash; 11:30 PM</span>
          <span class="evt-location">Modega, Long Island City</span>
          <span class="evt-type battle">Battle</span>
        </div>
        <div class="evt-desc">The grand finale! 7-to-Smoke and Jack &amp; Jill battle formats. Whether you're competing or cheering from the crowd, this is the moment everyone's been waiting for. Battle entry is limited to festival participants. Opening party with Waterparkjones from NSH San Diego.</div>
        <div class="evt-sub-timeline">
          <div class="evt-sub-item">
            <span class="evt-sub-time">6:45 PM</span>
            <span class="evt-sub-name">Opening Party &amp; Warm-Up</span>
          </div>
          <div class="evt-sub-item">
            <span class="evt-sub-time">8:00 PM</span>
            <span class="evt-sub-name">Preliminary Rounds</span>
          </div>
          <div class="evt-sub-item">
            <span class="evt-sub-time">9:00 PM</span>
            <span class="evt-sub-name">HNT Battle Finals</span>
          </div>
          <div class="evt-sub-item">
            <span class="evt-sub-time">10:30 PM</span>
            <span class="evt-sub-name">Closing Party</span>
          </div>
        </div>
        <div class="evt-expand-hint">tap for full battle schedule</div>
      </div>
    </div>

  </div>
</div>
```

**Step 2: Verify** — May 17 tab shows 3 named workshops + battle with venue and participant note.

**Step 3: Commit**
```bash
git commit -m "fix: update May 17 schedule with instructor names, venues, battle details"
```

---

## Task 9: Update Tickets Section

**Files:**
- Modify: `index.html` — `<section id="tickets">` (around line 960–1050)

**Step 1: Find all ticket CTA buttons** (they currently say "Coming in March" or similar) and update each to:
```html
<a href="#" class="btn-primary ticket-btn">Get Tickets</a>
```
Note: keep `href="#"` as placeholder until Ticket Tailor URLs are ready.

**Step 2: Add a note** below the ticket cards grid:
```html
<p class="tickets-note">Tickets available via <strong>Ticket Tailor</strong>. Individual workshop registration also available at checkout.</p>
```

**Step 3: Add CSS:**
```css
.tickets-note {
  text-align: center;
  margin-top: 2rem;
  color: var(--text-dim);
  font-size: 0.85rem;
}
.tickets-note strong { color: var(--text-muted); }
```

**Step 4: Verify** — all ticket buttons say "Get Tickets", note about Ticket Tailor appears below cards.

**Step 5: Commit**
```bash
git commit -m "fix: update ticket buttons and add Ticket Tailor note"
```

---

## Task 10: Add Housing Coordination Section

**Files:**
- Modify: `index.html` — insert after `</section>` of Tickets

**Step 1: Add HTML** after Tickets closing `</section>`:

```html
<!-- ========== HOUSING ========== -->
<section id="housing">
  <div class="container">
    <div class="section-header">
      <h2>Housing Coordination</h2>
      <p class="section-sub">Need a place to stay? We've got you covered.</p>
    </div>
    <div class="housing-content">
      <div class="housing-card">
        <div class="housing-icon">&#127968;</div>
        <h3>Coordinated by Reina</h3>
        <p>To The Music has a dedicated housing coordinator — Reina — who works with attendees to help find accommodations for the festival week. Whether you're looking to connect with other dancers for shared housing or just need recommendations, Reina can help.</p>
        <p class="housing-sub">Submit the form below and Reina will follow up with you directly.</p>
        <a href="#" class="btn-primary housing-btn" target="_blank" rel="noopener">Request Housing Coordination</a>
        <p class="housing-note">This opens a Google Form in a new tab. Reina will reach out via email.</p>
      </div>
    </div>
  </div>
</section>
```

**Step 2: Add CSS:**

```css
#housing { background: var(--bg-dark); }
.housing-content {
  display: flex;
  justify-content: center;
  margin-top: 2rem;
}
.housing-card {
  background: var(--bg-card);
  border: 1px solid #2a2a3a;
  border-radius: 16px;
  padding: 3rem;
  max-width: 580px;
  text-align: center;
}
.housing-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}
.housing-card h3 {
  font-family: 'Playfair Display', serif;
  font-size: 1.5rem;
  color: var(--text);
  margin-bottom: 1rem;
}
.housing-card p {
  color: var(--text-muted);
  line-height: 1.8;
  margin-bottom: 1rem;
}
.housing-sub {
  font-size: 0.9rem;
  color: var(--text-dim) !important;
}
.housing-btn {
  display: inline-block;
  margin: 1rem 0 0.5rem;
}
.housing-note {
  font-size: 0.8rem;
  color: var(--text-dim) !important;
  margin-bottom: 0 !important;
}
```

**Step 3: Verify** — Housing section renders with card and button. Button `href="#"` is placeholder.

**Step 4: Commit**
```bash
git commit -m "feat: add housing coordination section"
```

---

## Task 11: Add Map of Venues Section

**Files:**
- Modify: `index.html` — insert after Housing `</section>`

**Step 1: Create a custom Google Maps URL** with multiple markers. Use this embed approach — a single Google Maps iframe with a search query covering all venues. The cleanest approach for multiple pins is to create a Google My Maps at maps.google.com, add the pins, then use its embed URL. For now, use a placeholder iframe pointing to a map centered on Brooklyn/NYC:

```html
<!-- ========== MAP ========== -->
<section id="map">
  <div class="container">
    <div class="section-header">
      <h2>Festival Venues</h2>
      <p class="section-sub">All events take place across Brooklyn and Long Island City</p>
    </div>
    <div class="venues-list">
      <div class="venue-item">
        <span class="venue-dot" style="background:var(--accent)"></span>
        <div>
          <strong>Time Out Market BK</strong>
          <span>May 13 — Soul Records Laboratory</span>
        </div>
      </div>
      <div class="venue-item">
        <span class="venue-dot" style="background:var(--secondary)"></span>
        <div>
          <strong>El Santo, Bushwick</strong>
          <span>May 15 — All Workshops</span>
        </div>
      </div>
      <div class="venue-item">
        <span class="venue-dot" style="background:var(--gold)"></span>
        <div>
          <strong>Crossroads Cafe, Bushwick</strong>
          <span>May 16 — Love City NYC Afterparty</span>
        </div>
      </div>
      <div class="venue-item">
        <span class="venue-dot" style="background:#a78bfa"></span>
        <div>
          <strong>Modega, Long Island City</strong>
          <span>May 17 — All Workshops + Battle</span>
        </div>
      </div>
    </div>
    <div class="map-embed">
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d48372.27905887265!2d-73.97760599999999!3d40.7127753!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x89c25a22a3bda30d%3A0xb89d1fe6bc499443!2sBrooklyn%2C%20NY!5e0!3m2!1sen!2sus!4v1"
        width="100%"
        height="450"
        style="border:0;"
        allowfullscreen=""
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"
        title="Festival Venues Map">
      </iframe>
    </div>
    <p class="map-note">For a full interactive map with all venue pins, <a href="https://maps.google.com" target="_blank">view on Google Maps</a>.</p>
  </div>
</section>
```

**Note:** The iframe above is a placeholder centered on Brooklyn. The ideal final state is a Google My Maps with pins for all 4 venues — the organizer should create this at maps.google.com/maps/d and replace the `src` URL with the embed link from that custom map.

**Step 2: Add CSS:**

```css
#map { background: var(--bg-section); }
.venues-list {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  margin: 2rem 0;
  justify-content: center;
}
.venue-item {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  background: var(--bg-card);
  border: 1px solid #2a2a3a;
  border-radius: 8px;
  padding: 0.75rem 1rem;
}
.venue-dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  flex-shrink: 0;
}
.venue-item strong {
  display: block;
  color: var(--text);
  font-size: 0.9rem;
}
.venue-item span {
  display: block;
  color: var(--text-dim);
  font-size: 0.78rem;
}
.map-embed {
  border-radius: 12px;
  overflow: hidden;
  border: 1px solid #2a2a3a;
}
.map-note {
  text-align: center;
  margin-top: 1rem;
  font-size: 0.8rem;
  color: var(--text-dim);
}
.map-note a { color: var(--secondary); text-decoration: none; }
.map-note a:hover { text-decoration: underline; }
```

**Step 3: Verify** — Map section shows 4 venue pills and embedded map iframe.

**Step 4: Commit**
```bash
git commit -m "feat: add venues map section"
```

---

## Task 12: Add Merch Section

**Files:**
- Modify: `index.html` — insert after Map `</section>`

**Step 1: Add HTML:**

```html
<!-- ========== MERCH ========== -->
<section id="merch">
  <div class="container">
    <div class="section-header">
      <h2>Festival Merch</h2>
      <p class="section-sub">Represent To The Music on and off the dance floor</p>
    </div>
    <div class="merch-grid">

      <div class="merch-card">
        <div class="merch-img-wrap">
          <img src="assets/merch/tshirts.PNG" alt="To The Music T-Shirts — 3 colors" loading="lazy">
        </div>
        <div class="merch-info">
          <h3>Festival T-Shirt</h3>
          <p class="merch-desc">Comfort Colors heavyweight cotton. Available in 3 colorways. Sizes S–XL.</p>
          <div class="merch-price">$20</div>
        </div>
      </div>

      <div class="merch-card">
        <div class="merch-img-wrap">
          <img src="assets/merch/sweat_towels.PNG" alt="To The Music Sweat Towels — 3 colors" loading="lazy">
        </div>
        <div class="merch-info">
          <h3>Sweat Towel</h3>
          <p class="merch-desc">100% cotton terry cloth. Available in 3 colorways. The perfect dance floor companion.</p>
          <div class="merch-price">$5 <span class="merch-price-note">with t-shirt purchase</span></div>
        </div>
      </div>

    </div>
    <div class="merch-cta">
      <a href="#" class="btn-primary" target="_blank" rel="noopener">Order Merch</a>
      <p class="merch-note">Orders fulfilled via Ticket Tailor at checkout.</p>
    </div>
  </div>
</section>
```

**Step 2: Add CSS:**

```css
#merch { background: var(--bg-dark); }
.merch-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}
.merch-card {
  background: var(--bg-card);
  border: 1px solid #2a2a3a;
  border-radius: 12px;
  overflow: hidden;
  transition: transform 0.3s, border-color 0.3s;
}
.merch-card:hover {
  transform: translateY(-4px);
  border-color: var(--accent);
}
.merch-img-wrap {
  width: 100%;
  aspect-ratio: 4/5;
  overflow: hidden;
  background: #0d0d14;
}
.merch-img-wrap img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.merch-info {
  padding: 1.5rem;
}
.merch-info h3 {
  font-family: 'Playfair Display', serif;
  font-size: 1.2rem;
  color: var(--text);
  margin-bottom: 0.5rem;
}
.merch-desc {
  color: var(--text-muted);
  font-size: 0.9rem;
  line-height: 1.6;
  margin-bottom: 1rem;
}
.merch-price {
  font-size: 1.4rem;
  font-weight: 700;
  color: var(--accent);
}
.merch-price-note {
  font-size: 0.8rem;
  color: var(--text-dim);
  font-weight: 400;
}
.merch-cta {
  text-align: center;
  margin-top: 2.5rem;
}
.merch-note {
  margin-top: 0.75rem;
  font-size: 0.8rem;
  color: var(--text-dim);
}
```

**Step 3: Verify** — Merch section shows 2 product cards with images, prices, and an Order Merch button.

**Step 4: Commit**
```bash
git commit -m "feat: add merch section with t-shirts and sweat towels"
```

---

## Task 13: Add Instagram Section

**Files:**
- Modify: `index.html` — insert after Merch `</section>`

**Step 1: Add HTML:**

```html
<!-- ========== INSTAGRAM ========== -->
<section id="instagram">
  <div class="container">
    <div class="section-header">
      <h2>Follow Along</h2>
      <p class="section-sub">
        <a href="https://instagram.com/tothemusicnyc" target="_blank" rel="noopener" class="ig-handle">@tothemusicnyc</a>
      </p>
    </div>
    <div class="ig-embed-wrap">
      <!-- Behold.so Instagram feed widget — replace the div below with your Behold embed code -->
      <!-- To set up: create a free account at behold.so, connect @tothemusicnyc, copy the embed snippet -->
      <div class="ig-placeholder">
        <p>Instagram feed coming soon</p>
        <a href="https://instagram.com/tothemusicnyc" target="_blank" rel="noopener" class="btn-secondary">View on Instagram</a>
      </div>
    </div>
  </div>
</section>
```

**Step 2: Add CSS:**

```css
#instagram { background: var(--bg-section); }
.ig-handle {
  color: var(--accent);
  text-decoration: none;
  font-size: 1.1rem;
}
.ig-handle:hover { text-decoration: underline; }
.ig-embed-wrap {
  margin-top: 2rem;
}
.ig-placeholder {
  text-align: center;
  padding: 4rem 2rem;
  background: var(--bg-card);
  border: 1px dashed #2a2a3a;
  border-radius: 12px;
  color: var(--text-dim);
}
.ig-placeholder p { margin-bottom: 1.5rem; }
```

**Step 3: Verify** — Instagram section renders with placeholder and "View on Instagram" button.

**Note for later:** When Behold.so is set up, replace the `<div class="ig-placeholder">...</div>` with the Behold embed snippet. It will look like:
```html
<div id="behold-widget-XXXXXXXX"></div>
<script>
  window.BEHOLD_WIDGET_SCRIPT = ...
</script>
```

**Step 4: Commit**
```bash
git commit -m "feat: add instagram section with behold.so placeholder"
```

---

## Task 14: Add Contact Section

**Files:**
- Modify: `index.html` — insert after Instagram `</section>`, before `<footer>`

**Step 1: Add HTML:**

```html
<!-- ========== CONTACT ========== -->
<section id="contact">
  <div class="container">
    <div class="section-header">
      <h2>Get In Touch</h2>
      <p class="section-sub">Questions? We're here to help.</p>
    </div>
    <div class="contact-grid">

      <div class="contact-card">
        <div class="contact-icon">&#9993;</div>
        <h3>Email</h3>
        <p>For general inquiries about the festival:</p>
        <a href="mailto:hello@tothemusicnyc.com" class="contact-link">hello@tothemusicnyc.com</a>
        <p class="contact-note">(update email address as needed)</p>
      </div>

      <div class="contact-card">
        <div class="contact-icon">&#128247;</div>
        <h3>Instagram</h3>
        <p>Follow us for announcements, schedule updates, and behind-the-scenes content:</p>
        <a href="https://instagram.com/tothemusicnyc" target="_blank" rel="noopener" class="contact-link">@tothemusicnyc</a>
      </div>

      <div class="contact-card">
        <div class="contact-icon">&#127968;</div>
        <h3>Housing</h3>
        <p>Need help with accommodations for the festival week?</p>
        <a href="#housing" class="contact-link">Request Housing Coordination &rarr;</a>
      </div>

    </div>
  </div>
</section>
```

**Step 2: Add CSS:**

```css
#contact { background: var(--bg-dark); }
.contact-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1.5rem;
  margin-top: 2rem;
}
.contact-card {
  background: var(--bg-card);
  border: 1px solid #2a2a3a;
  border-radius: 12px;
  padding: 2rem;
  text-align: center;
  transition: border-color 0.3s;
}
.contact-card:hover { border-color: var(--accent); }
.contact-icon {
  font-size: 2rem;
  margin-bottom: 0.75rem;
}
.contact-card h3 {
  font-family: 'Playfair Display', serif;
  font-size: 1.1rem;
  color: var(--text);
  margin-bottom: 0.5rem;
}
.contact-card p {
  color: var(--text-muted);
  font-size: 0.85rem;
  line-height: 1.6;
  margin-bottom: 0.75rem;
}
.contact-link {
  color: var(--accent);
  text-decoration: none;
  font-size: 0.9rem;
  font-weight: 500;
}
.contact-link:hover { text-decoration: underline; }
.contact-note {
  font-size: 0.75rem;
  color: var(--text-dim) !important;
  margin-top: 0.25rem;
  margin-bottom: 0 !important;
}
```

**Step 3: Verify** — Contact section shows 3 cards: email, Instagram, housing link.

**Step 4: Commit**
```bash
git commit -m "feat: add contact section"
```

---

## Task 15: Update CLAUDE.md Feature Status

**Files:**
- Modify: `CLAUDE.md` — Feature Status section

**Step 1: Update the status table** to reflect completed work — move all newly built sections from "Not Started" / "Incomplete" to "Complete", and update placeholders list.

**Step 2: Commit**
```bash
git commit -m "docs: update CLAUDE.md feature status"
```

---

## Placeholders to Fill In Later

| Item | Where | What's needed |
|------|-------|---------------|
| Ticket Tailor URLs | Ticket buttons + Merch CTA | Ticket Tailor account + event links |
| Google Form URL | Housing section button | Reina's Google Form link |
| Contact email | Contact section | Actual email address |
| Behold.so embed | Instagram section | Connect @tothemusicnyc at behold.so |
| Google My Maps | Map section iframe src | Create custom map with venue pins at maps.google.com |
| Teacher bios + photos | Teachers section | Photos and bio text per instructor |
| Party organizer details | About section | Announced closer to festival month |
| May 14 potluck location | Schedule May 14 | Venue TBD |
