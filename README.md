# 🦖 Icarus Breeding Tracker

A herd tracker and breeding planner for the game [Icarus](https://store.steampowered.com/app/1149460/Icarus/). Track your animals, plan breeding pairs, manage bloodlines and phenotypes, and record lineage — all in a single file with no install, no account, and no internet required.

---

## 🌐 Recommended: Use the Web Version

The easiest way to use the app is directly in your browser — nothing to download or update:

**https://rnksekmeth.github.io/icarus-breeding-tracker**

The web version is always up to date with the latest features. Your data is saved to a local JSON file on your own computer using the File System Access API — nothing is sent to any server.

> **Browser requirement:** Chrome or Edge (version 86+). Firefox does not support the File System Access API. The app will work in Firefox using browser storage as a fallback, but local file saving requires Chrome or Edge.

---

## 💾 Alternative: Download and Run Locally

If you prefer to keep a local copy (useful for offline play or if you want a specific version):

### Option A — Download the file directly

1. Go to the [repository on GitHub](https://github.com/rnksekmeth/icarus-breeding-tracker)
2. Click `index.html` in the file list
3. Click the **download icon (⬇)** in the top right of the file view
4. Save it to a permanent local folder, e.g. `E:\Icarus\BreedingTracker\index.html`
5. Open it in Chrome or Edge

> Avoid saving to a cloud-synced folder like OneDrive or Google Drive — file syncing can occasionally conflict with auto-save. A local drive is ideal.

### Option B — Clone with Git

```
git clone https://github.com/rnksekmeth/icarus-breeding-tracker.git
```

Pull updates with `git pull` whenever a new version is released.

---

## 🚀 First Launch

1. Open the app (web version or local file) in Chrome or Edge
2. A startup screen appears asking how to store your data
3. Click **✨ Start fresh (create new file)**
4. A save dialog opens — pick any folder and save as `herd_data.json`
5. The app is ready to use

On every future visit, the app remembers your file. Click **▶ Continue with herd_data.json** and grant permission when prompted — a one-click step each session.

### Migrating from an older version

If you previously used the app when it stored data in the browser, click **⬆ Migrate data from browser storage** on the startup screen. Your data will be exported to the new file format and the old browser storage will be cleared.

---

## 💾 Saving

The app saves automatically after every change. A small **💾 Saved** indicator appears briefly in the top right to confirm each save. You never need to save manually.

Your `herd_data.json` file can be backed up, copied to another computer, or shared with other players like any regular file.

---

## 📖 How to Use

### ➕ New Animal

Fill in the species, sex, bloodline, phenotype, generation, stats (VIG, FIT, PHY, REF, TGH, ADP, INS), and optionally the parents. The app generates a name automatically in the format `DR01 55F-Bold P3 VIG2`. Hover over any stat label or column header to see what the stat does.

After saving, a **Place in Breeding Pair** panel appears offering to slot the animal directly into a pair. The app scores all available slots and highlights the best suggestion. If a slot already has an occupant, you can choose what happens to the displaced animal.

### 📋 My Herd

Shows all your animals in a sortable, filterable table. Key features:

- **Sort** by any column — click a header once to sort, again to reverse
- **Filter** by species, status, sex, bloodline, phenotype, and minimum total score
- **Change status inline** — each row has a status dropdown; no need to open Edit Animal
- **Edit** an animal with the edit button; a **Cancel** button lets you exit without saving changes
- **🪦 Show Dead** toggle to include or exclude dead/culled animals from the view

### 🔀 Breeding Pairs

Set up your active breeding pairs per species. The app enforces global exclusivity — an animal can only appear in one pair slot at a time. Dune Raptors and Swamp Raptors can be cross-bred; their animals appear in each other's pair slots.

Each pair shows a goal badge indicating whether the current animals match your set bloodline and phenotype goals. An upgrade recommendation panel below suggests free animals that could improve the weakest pair slot.

### ⚙ Goals

Per-species configuration:

- **Breed-out stat** — the stat you are breeding toward 0 (excluded from the total score and animal name). Default is VIG. For animals that cannot be ridden or don't produce resources, consider INS instead.
- **Pair goals** — set a target bloodline and phenotype for each pair slot
- **Priority weights** — star-rate bloodlines and phenotypes to influence the scoring and advice system
- **Phenotype sightings** — tracks how many tamed vs bred animals of each phenotype you've seen

### 🧬 Lineage

Select any animal to view its family tree up to 4 generations deep. Each node shows stats, bloodline, generation, and inheritance indicators — whether each stat was inherited from the mother, father, improved beyond both parents, or regressed.

The sidebar shows species-level breeding insights: average stat gain per breeding, best performing stat trend, and total recorded animals.

---

## 🐾 Status Reference

| Icon | Status | Meaning |
|---|---|---|
| ❓ | Undecided | Newly added, not yet assessed |
| ✅ | Keep | Good animal, part of the herd long-term |
| 🐣 | Breed | Active breeder |
| ⚡ | Temp Breed | Temporary breeder — wrong bloodline but used for a stat boost |
| 🔶 | Reserve | Held in reserve, not currently active |
| 🛸 | On Station | Stored on the space station (transit between maps or safe storage) |
| 🗑️ | Discard | Scheduled for removal |
| 🪦 | Dead/Culled | Deceased — hidden by default, kept in records |

---

## 🧬 Species Reference

| Species | Code | Notes |
|---|---|---|
| Dune Raptor | DR | Can cross-breed with Swamp Raptor |
| Swamp Raptor | SR | Can cross-breed with Dune Raptor |
| Moa | BM | Mount and fast travel animal |
| Slinker | SL | |

Cross-breed offspring are either a DR or SR (not a hybrid) — determined by which species tab the pair is in.

> **Note:** Cross-breeding between Dune Raptors and Swamp Raptors may become unavailable in a future game update once each species receives its own skill tree.

---

## 💬 Feedback & Bug Reports

Use the **⚙ Settings** tab inside the app for direct links to submit bug reports and feature requests on GitHub. A free GitHub account is required to post, but anyone can view existing issues.

Direct links:
- 🐛 [Report a Bug](https://github.com/rnksekmeth/icarus-breeding-tracker/issues/new?labels=bug)
- ✨ [Feature Request](https://github.com/rnksekmeth/icarus-breeding-tracker/issues/new?labels=enhancement)
- 📋 [View All Issues](https://github.com/rnksekmeth/icarus-breeding-tracker/issues)

---

## 🤝 Sharing the App

Share the `index.html` file directly — it is completely self-contained. Recipients follow the same first launch steps to set up their own data file. Or just send them the web version link.
