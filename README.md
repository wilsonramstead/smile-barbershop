# Smile Barbershop — demo site

Demo site built by Wilson Innovations for **Smile Barbershop**, 3009 US-92, Suite 3, Winter Haven, FL 33881.

- **Live:** https://wilsoninnovations.net/smile-barbershop/
- **Wave:** 70 (lead index 3)
- **Built:** 2026-08-21
- **Status:** unpitched demo — `noindex` is active, remove it when the shop goes live.

## Provenance

Every business fact on this page comes from the wave 70 manifest entry, sourced from the shop's Google
Business Profile via the Google Places API and **re-fetched and re-verified during this build**. Phone,
address, rating, review count, opening hours and all five review texts matched the manifest exactly on
re-fetch (`places.googleapis.com/v1/places:searchText`, place id `ChIJe_QDPQBt3YgR2Agcqdp9mMg`).

| Fact | Value | Source |
| --- | --- | --- |
| Phone | (863) 303-2460 | GBP — **matches the number painted on the shop's own door** |
| Address | 3009 US-92, Suite 3, Winter Haven, FL 33881 | GBP, confirmed against the storefront photo (Suite 3, commercial plaza) |
| Rating | 4.9 | GBP (≥4.7, so it appears in the hero trust chip) |
| Reviews | 37 | GBP |
| Hours | Tue–Fri 9–6, Sat 8–5, Mon + Sun closed | GBP, presented with a call-ahead softener (see below) |
| Website | none | GBP lists no website — this is a first-website pitch |
| Google Maps | cid 14454441382139136216 | GBP `googleMapsUri`, used for the address/directions links |

### The owner's name is spelled three different ways — confirm it on the call

The five surfaced Google reviews name the owner-barber **three different ways**:

- Melo P. — *"the **owner Alex** very nice and professional"* (the only review that says *owner*)
- J. S. — *"**Alex** is always my go to"*
- Davila's Remodeling — *"The true star of this place is **Alexi**, the best barber you can find"*
- Julian Z. — *"**Alexis** and the team are true professionals"*

The manifest settles on **Alex**, and the site uses that spelling exactly **once**, in body copy in the
"line-up" section ("Regulars ask for Alex by name…"). It is deliberately **not in the hero, the title,
the meta description or the JSON-LD**. Reviews keep whatever spelling the reviewer wrote — those quotes
are verbatim, so "Alexi" and "Alexis" appear as-is.

**Ask him on the call which spelling is right**, then it can move into the headline. It is also a
natural opener: *"your reviewers spell your name three different ways — that's the kind of thing a
website fixes."*

### Hours check against the door lettering — MISMATCH, and it's the pitch opener

Per the SC Barbershop (wave 69) lesson, the storefront photo was zoomed and the painted lettering
compared line by line against the Google schedule:

- **Painted phone: 863-303-2460 — MATCHES the GBP phone.** (A second line, 863-303-2958, is painted
  under it. It is not on the GBP, so it is **not used anywhere on the site**.)
- **Painted hours: they do NOT match Google.** The business-hours placard on the door reads
  `Mon. - Tue. 9am - 6pm / Wed. 10am - 7pm / Thur. - Fri. 9am - 6pm / Sat. 8am - 5pm / Sunday - Closed`,
  while Google says **Monday closed** and **Wednesday 9–6**. Two contradictions: the door says the shop
  is open Mondays, and the door says Wednesday starts an hour later and ends an hour later.
  (The placard is at the resolution limit of the photo — the line structure and the "10am–7pm"
  Wednesday line are clear, individual characters are not. Treat it as "very likely" and confirm.)

That is a customer walking up on a Monday to a locked door, or showing up at 9am on a Wednesday.
**Lead the call with it.** The site itself ships the Google hours plus a softener — "Hours as listed on
Google. Barbers book up and Saturdays fill fast — give the shop a quick call before you make the drive"
— so nothing on the page is wrong either way.

### Deliberately left out

- **No pricing, no founding year, no license number, no email, no staff roster** — none of it is evidenced.
  (A framed certificate is visible on the wall in one photo but is completely illegible, so no
  "licensed" claim is made anywhere.)
- **No booking link and no social links.** The door glass shows a booking-app handle and an Instagram
  handle (`Smile_Barbershop`), but neither is on the GBP and neither was verified, so neither is linked.
  Worth confirming on the call — a working booking button would be an easy add.
- **No owner-personality section.** One name mention, no shrine.
- **No walk-in / appointment-only claim** — the policy is not stated anywhere in the source material.
- **No second phone number** (see above).
- **Service list stays inside the evidence**: fades, tapers, line-ups, beard trims/blends, family and
  kids' cuts, hair designs — all supported by the reviews and by the shop's own photos.
- **Review quotes are verbatim and contiguous**, attributed first name + last initial, **no dates**.
  J. S.'s review keeps its original line breaks rather than being re-punctuated into sentences.
  The aggregate 4.9 / 37 / US-92 row is styled as a stat panel, never as a quote.

## Images

**Every photo on this site is the business's own.** All ten photos on the GBP are attributed to
*Smile Barbershop* itself (zero customer-contributed images), pulled through the Places API photo
endpoint. **No stock photography was used** — this build has **no Unsplash photo IDs at all** and
therefore cannot collide with any sibling site in the portfolio.

Every image was opened and looked at before use. Processing: PIL re-encode, longest edge ≤1600px,
**all files ≤350KB**, self-hosted under `img/`. No readable license plates, no readable personal
documents, no minors' faces (the two shots that may be of younger clients are back-of-head only, with
no face visible).

| File | Content | Role |
| --- | --- | --- |
| `shop-neon.jpg` | Barber chair under the neon Smile sign, violet shop lighting | hero card |
| `storefront.jpg` | Storefront, Suite 3, sign + barber pole + window lettering | og:image + Visit panel |
| `barber-at-work.jpg` | Barber checking a client's fade at the station | "line-up" feature |
| `curly-taper-fade.jpg` | Curly taper with blended beard | gallery |
| `design-lineup.jpg` | Carved design line and fade, neon sign behind | gallery |
| `classic-cut.jpg` | Classic cut, sharp line-up, profile | gallery |
| `taper-shopfloor.jpg` | Curly taper with the shop floor behind | gallery |
| `silver-blend.jpg` | Silver hair blended and squared off | gallery |
| `branded-cape.jpg` | Client in the shop's branded cape after a cut | gallery |

One GBP photo was **not used**: a mirror selfie of the barber with a visitor. The image is
horizontally flipped, so the shop's own logo and lettering read backwards in it.

## Build

Self-contained single `index.html` — inline CSS and ~30 lines of inline JS, no build step, no external
JavaScript. Works from `file://`.

- **Tier 2 — Showpiece / Night Shift**: drifting aurora blob field + film grain, glass cards, gradient
  text fills on headline words, gradient CTA with a shine sweep, a marquee ticker, and one-shot
  blur/translate scroll reveals.
- **Palette**: matte charcoal `#0A0A0C` / `#131316` with **bright smile-yellow** `#FFD028` → `#F5A800`
  and crisp white. This is the **only yellow in the barber portfolio** and it is deliberately a *sunny*
  yellow, not a metallic gold — it reads clearly apart from Jr Champions' championship gold on navy and
  Cutz of Blessingz' halo-gold on ink, and it shares nothing with SC Barbershop's electric blue,
  Barberiish's oxblood/copper, Court-Side's maple/orange, Lagena's teal/coral or The Barber Co's
  graphite/rose-brass. A low-opacity violet blob in the aurora picks up the shop's real neon lighting.
  *(Note for the call: the shop's actual logo is navy/red/white. The yellow here is a proposal keyed to
  the "Smile" name — and it avoids colliding with the other Winter Haven barbershop's blue.)*
- **Fonts**: Unbounded (display) + Mulish (body).
- **Mobile**: H1 is exactly 2 lines at 390px, zero horizontal overflow at 390 / 1366 / 1440
  (`scrollWidth === clientWidth` at all three), icon-only header call button flush right ≤600px,
  all tap targets ≥44px, **no fixed bottom call bar**.
- **Hero stack** (eyebrow → headline → sub → CTA pair → trust chips) is fully visible with no scroll at
  1440×900 and 1366×768; on mobile both CTAs and all three chips land in the first 390×844 viewport.
- **Motion** is gated behind `prefers-reduced-motion`; scroll reveals are gated behind a `js` class, so
  with JavaScript disabled the page renders complete and fully readable (verified).
- `BarberShop` JSON-LD with address, phone, `hasMap`, aggregate rating and opening hours.

## Pitch context (not site copy)

1. **No website at all** — this is a first-website conversation, not a rebuild.
2. **The door hours contradict Google** (details above). Concrete, costs him customers, easy to fix.
3. **His own name is spelled three ways in his own reviews.** A website is the one place he controls it.
4. **He has ten good photos already** — this whole demo is built from them, no stock. That is the
   "this is your shop, not a template" moment on the call.
5. Julian Z.'s review says he has been to shops in **Lakeland and Auburndale** and none match this one —
   there is a wider service area than the Winter Haven address implies.
