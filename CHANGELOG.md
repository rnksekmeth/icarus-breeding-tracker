# Changelog – Icarus Breeding Tracker

All notable changes to this project are documented here.

---

## v0.14 – New Animal Polish
**2026-04-05**

- New Animal: parent datalist now shows one entry per animal (spId · name format) — no more duplicate or partial entries from prior field state
- New Animal: ⚠ THEORY ONLY disclaimer moved to the bottom of the probability panel
- New Animal: 🗑 Clear button added to reset the form without navigating away; pair-assign and prob panels are also dismissed; button is hidden/inert when editing an existing animal

---

## v0.13 – Ordering & Suggestions
**2026-04-05**

- Breeding Pairs + Goals: drag-and-drop species card reordering (shared order, drag by ⠿ handle); order persists to save file
- Breeding Pairs: collapsed species cards now sort to the bottom of the grid automatically
- Breeding Pairs + Goals: ▣ 2-wide / ◧ 1-wide toggle per species card; persists to save file
- Goals: Breeding Suggestions panel per species — shows priority animals not in pairs (by bloodline/phenotype stars), reserve candidates (desired trait but lower stats), and per-pair recommendations; Unstable treated as a breeding priority in scoring
- Goals + New Animal: reserve target per species — set desired number of reserve animals; current vs target shown in New Animal tab when species is selected; Unstable flagged as a breeding priority
- New Animal: parent fields changed to neutral "Parent 1 / Parent 2" — either field accepts either parent; save now validates that two known parents must be opposite sex

---

## v0.12 – Sightings, Pairs & Filters
**2026-04-05**

- Share Your Herd: phenotype now colored by rarity (grey/green/blue/orange); bloodline now colored with a fixed per-bloodline palette (same system used throughout the app)
- Goals: editing an animal now correctly adjusts bloodline and phenotype sighting counts — changing Alpha → Savage decrements Alpha and increments Savage; isBred flag changes (adding/removing parents) are also handled
- Pairs: each pair row now has a red × delete button — removes that specific pair regardless of position, and automatically sets both animals in the pair to 🔶 Reserve
- My Herd: phenotype filter pills now show positional labels only (Base, P1, P2…) so cross-species filtering works correctly — selecting P1 shows all P1 animals regardless of species; "Dune Raptor (base)" and "Normal (base)" both appear as "Base"

---

## v0.11 – Quality of Life
**2026-04-05**

- Share Your Herd: added "Best of species…" mode with species selector and top-N count; added "Custom selection…" mode with per-animal checkboxes; species label on cards now shows "DR – Dune Raptor" format
- Pairs tab: collapse/expand ▼/▶ button per species card to minimise sections; top toolbar with species dropdown + "Add Pair Slot" button for quick pair management
- My Herd: 🛸 Show Station toggle added next to 🪦 Show Dead, so you can see station animals when planning new breeding
- Goals: Bloodline Sightings section added per species card (same format as Phenotype Sightings, 🌿 tamed / 🧬 bred); `blStats` added to persisted data

---

## v0.10 – Wiki Links & Herd Share
**2026-04-05**

- Wiki link button added to each species card header in the Breeding Pairs tab — opens the species page on icarus.wiki.gg in a new tab
- Species shorthand in Pairs tab fixed: was showing D/S/M/K, now correctly shows DR/SR/BM/SL (species-dot + full name + code badge, matching the Goals tab)
- `SPECIES_DATA` extended with `wiki` URL per species; `icon` field removed
- Future species data saved as a code comment in `SPECIES_DATA` for later implementation (mounts, station pets, pair management scaling notes)
- New 📸 Share Your Herd section in Settings — generates a canvas image of your animals with four modes: Top 10, Best per Species, Active Breeders, All Active
- Image is copied to clipboard automatically; a download link is shown as a fallback if clipboard API is unavailable
- README: Moa description corrected from "production animal" to "mount and fast travel animal"
- README: Cross-breed disclaimer added noting DR/SR cross-breeding may change when separate skill trees are introduced

---

## v0.9 – Tooltips & Station
**2026-04-05**

- Hover tooltips on all stat labels (form and table headers): full name and what the stat affects
- Hover tooltips on bloodline cells in My Herd with fixed stats and growth stat effects for all 12 bloodlines
- Hover tooltips on species abbreviation cells showing the full species name
- New 🛸 On Station status — for animals stored on the space station between maps
- Station animals are excluded from pair slots (same as Dead/Culled)
- GitHub feedback buttons added to Settings tab: Report a Bug, Feature Request, View All Issues
- README rewritten: web version recommended first, status reference table added, all sections expanded and updated

---

## v0.8 – Pair Assignment
**2026-04-05**

- After saving a new animal, a "Place in Breeding Pair" panel appears below the form
- App scores all compatible pair slots and highlights the best suggestion (empty slots prioritised, then by score improvement)
- Dropdown selectors for species and pair number let the user override the suggestion; sex slot is fixed to the animal's sex
- If the chosen slot already has an occupant, the panel shows their name and score with three options: keep their status unchanged, move them to Reserve, or mark as Discard
- Placing an animal auto-updates their status from ❓/Keep to 🐣 Breed
- Panel is dismissed when the user starts a new entry or clicks Skip

---

## v0.7 – Inline Status & Settings
**2026-04-05**

- Inline status dropdown on every herd row — change status without opening Edit Animal
- Status icons added throughout: ❓ Undecided, ✅ Keep, 🐣 Breed, ⚡ Temp Breed, 🔶 Reserve, 🗑️ Discard, 🪦 Dead/Culled
- Status filter bar updated with icons; ❓ Undecided added as a filter option
- New ⚙ Settings tab — houses data management tools in one place
- Moved Clear All to Settings tab with explicit confirmation checkbox and final-action warning
- Cancel button in Edit Animal form — returns to My Herd with no changes saved

---

## v0.6 – Sort & Filter
**2026-04-05**

- Sort arrows on every column header, updating live to show ↑/↓ on the active column
- Fixed sort for Species, Bloodline, Phenotype and Sex (were falling through to wrong fields)
- New filter row: Sex (All / ♂ M / ♀ F)
- New filter row: Bloodline — dynamic pills built from animals currently in the herd
- New filter row: Phenotype — dynamic pills built from animals currently in the herd
- New filter: Min Total ≥ number input
- Added Sex column to herd table (♂/♀ with gender colours)

---

## v0.5 – Data Migration
**2026-04-05**

- Add `DATA_VERSION` constant — bump this whenever a schema change requires migration
- `loadedDataVersion` captured on load so migrations know where to start
- `migrateMemory()` now runs versioned steps in order (v1→v2→v3→...→current)
- localStorage fallback correctly treated as v1 (pre-version-field data)
- Future schema changes need only a single `if (loadedDataVersion < N)` block
- Data automatically re-saved after migration so the file is always up to date

---

## v0.4 – Cross-breeding
**2026-04-05**

- DR and SR animals can now be placed in each other's pair slots for cross-breeding
- Cross-species animals shown in dropdowns with a [SR]/[DR] tag to distinguish them
- Offspring species is implied by which tab the pair lives in
- Added disclaimer in DR/SR pair sections noting the mechanic will change in a future update
- `CROSS_BREEDS` config added — extend with one line if new cross-breed species are added
- Pair exclusivity is now global across all species (not just within one species)

---

## v0.3 – Pair Exclusivity
**2026-04-05**

- Animals assigned to a pair are no longer available in other pair dropdowns
- Added safety guard in updatePair to reject duplicate assignments with a toast message

---

## v0.2 – Local File Storage
**2026-04-05**

- Replace localStorage with File System Access API
- Startup modal: open existing file, create new, or migrate from browser storage
- Auto-save to `herd_data.json` with debounce + "💾 Saved" indicator
- File handle persisted via IndexedDB (no re-picking on relaunch)
- Falls back to browser storage if File System Access API unavailable
- Add version label to header

---

## v0.1 – Initial Release
**2026-04-05**

- Single-file HTML app, no install needed
- Four species: Dune Raptor (DR), Swamp Raptor (SR), Moa (BM), Slinker (SL)
- Per-species sequential IDs (e.g. DR01, BM03)
- 7 stats: VIG, FIT, PHY, REF, TGH, ADP, INS; configurable breed-out stat
- Generated animal name format: `DR01 48F-Wild P3 VIG2`
- Phenotype rarity colours: Base / Uncommon / Rare / Legendary
- Phenotype occurrence counter (tamed vs bred)
- Animal statuses: Keep, Breed, Temp, Reserve, Discard, Dead (soft delete with restore)
- Pair planner with breeding advice panel
- Probability panel with ⚠ THEORY ONLY disclaimer
- Quick-remove button on advice panel items
- CSV export and import
- Lineage viewer
- Published on GitHub Pages
