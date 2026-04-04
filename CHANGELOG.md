# Changelog – Icarus Breeding Tracker

All notable changes to this project are documented here.

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
