# His Presence Fire Ministries — build notes

**Type:** Lovable rebuild (CLAUDE.md §0 case B) — but WDF held real onboarding details for this
church, so v1 used real content, not placeholders.

## Brand
- Palette: `gold` — ink `#12100A` (near-black), ash `#1E1A10` (dark brown), ember/blaze/gold
  golds, bone `#F6F0E2` off-white. Chosen because it already matches the church's own colours
  (Black, White, Brown, Gold) — no remap needed.
- Theme imagery: fire / flame / stained glass / worship / golden light.
- Hero: "Encounter his presence," / "live in his fire."
- Scripture: Matthew 3:11 ("He will baptise you with the Holy Spirit and with fire.")

## Real details used (from WDF app onboarding, not placeholders)
- Service time: Sundays 10:30 – 13:30 (Sunday Celebration line in Times & Place)
- Address: 2396 Section N, Mangaung — also wired into the Google Maps embed query
- Pastor's cell: 069 825 5230 — wired as `tel:` link in the Visit CTA and shown in the footer

## Post-generate manual edits
The generator's template ships generic Sunday/Wednesday/Friday service slots and a placeholder
phone number. Updated after generate.py ran:
- Sunday service time → 10:30 – 13:30
- Address line + map embed → 2396 Section N, Mangaung
- `tel:` links → +27698255230, visible number added to footer

Wednesday Bible Study (18:00) and Friday His Presence Night (18:30) are template defaults —
not confirmed by the brief. Confirm or correct with the church if they differ.

## Phase 2 — refine (2026-07-19)
Rebuilt against the church's real Lovable site (hispresencefireministries.lovable.app) using
screenshots + the site's own rendered HTML (fetched directly — it's server-rendered, so the
full copy deck and asset URLs were readable without a browser).

**Logo/brand carried across:**
- Downloaded the church's actual flame+cross logo from the Lovable site's asset host, cropped
  out the excess canvas, and knocked out the white background → `assets/img/logo-mark.png`
  (icon only, used in nav/hero/footer/favicon) and `logo-full.png` (icon+wordmark, unused
  currently, kept in case a future section wants the full lockup).
- Hero background: carried across the church's own hero photo (worshipper, one hand raised,
  gothic stained glass, warm light) directly from the Lovable asset host rather than
  re-sourcing via Pexels — Pexels had no equivalent (modern worship-hall/stage-light photos
  only, no literal stained glass), and the brief asked to carry across "the hero image feel."
  This is the one deliberate exception to the Pexels-first image rule in CLAUDE.md §7.

**Images replaced (v1 Pexels choices didn't fit):**
- `welcome.jpg` was a Catholic priest at an ornate marble altar — swapped for a black-clergy
  figure in silhouette, hand raised, warm cathedral light (Pexels 7219011, MART PRODUCTION).
- `moment-3.jpg` (community) was a generic stock high-five photo with no church context —
  swapped for an actual volunteer/outreach scene (Pexels 6646923, RDNE Stock project).
- `visit.jpg` had Christmas pine branches in frame — swapped for a plain candle-flame close-up
  (Pexels 2563040, Andre Moura), on-theme for "fire" and season-neutral.
- Kept `moment-1.jpg` (choir/worship) and `moment-2.jpg` (prayer) — already strong fits.

**Content — restructured around the church's real copy, not template filler:**
- Hero: real tagline capitalization ("Encounter His Presence, live in His fire."), real vision
  sentence as the subhead, "A Christ-centered ministry" eyebrow (their own line), flame mark
  added as a one-time signature moment above the headline (nav/footer keep it small).
- Welcome section → Vision section: real two-paragraph vision (Trinity, new birth, water +
  Spirit baptism), real headline "A generation set ablaze for Christ." (their own line).
- "What to expect" (id was `#expect`, now `#mission`) → Mission section: real "equip and
  empower" mission line + all five real pillars (Training & Development, Gospel Proclamation,
  Spiritual Leadership, Spiritual Growth, Hope & Direction).
- Kept the pinned/scaled Matthew 3:11 moment as-is — it's the site's "one strong moment" the
  brief asked for and was already built in v1.
- Added a new `#foundation` section ("Anchored in the Word.") — the four foundation verses as
  a set (John 14:6, John 1:1, Matthew 28:19, Matthew 3:11), matching the original site's
  scripture grid, placed right after the pinned Matthew 3:11 moment.
- Visit CTA headline → "Come as you are. Leave transformed." (their real connect-section line,
  period punctuation matches the original) with their real supporting sentence. The Moments
  gallery heading uses the comma variant ("Come as you are, leave transformed") — intentional
  refrain, not a duplication bug.
- Nav/footer links renamed to match: Vision / Scripture / Mission / Times & place / Give
  (+ Ministries in the footer). Ministries section (Prayer & Intercession / Worship & Praise /
  Youth on Fire / Community Outreach) kept as-is — practical "get involved" groups, distinct
  from the doctrinal Mission pillars, not contradicted by the brief.

**Deliberately left out:** the `hello@hispresencefire.org` mailto and the hardcoded "© 2026"
footer from the Lovable original — both confirmed present on their site but flagged by the
operator as an unverified template pattern. No email link added anywhere. The footer year was
already dynamic (`new Date().getFullYear()`) in our template, not a hardcoded placeholder, so
nothing needed changing there.

Verified by rendering the live page in headless Chrome (screenshotted hero + full scroll) —
layout, fonts, real copy, map (correctly geolocates to Mangaung/Bloemfontein), and images all
confirmed working before push.
