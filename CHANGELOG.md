# Changelog – Icarus Breeding Tracker

All notable changes to this project are documented here.

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
