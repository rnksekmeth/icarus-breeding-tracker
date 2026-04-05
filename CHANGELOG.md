# Changelog – Icarus Breeding Tracker

All notable changes to this project are documented here.

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
