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
