# 🦖 Icarus Breeding Tracker

A herd tracker and breeding planner for the game [Icarus](https://store.steampowered.com/app/1149460/Icarus/). Single HTML file — no install, no account, no internet required after download.

Your data is saved to a local JSON file on your computer that you choose on first launch.

---

## Requirements

- **Chrome** or **Edge** (version 86 or newer)
- No other software needed

> Firefox is not supported — it does not implement the File System Access API used for local saving. The app will offer a browser storage fallback, but local file saving requires Chrome or Edge.

---

## Getting the App

### Option A — Download from GitHub (recommended)

1. Go to the [repository on GitHub](https://github.com/rnksekmeth/icarus-breeding-tracker)
2. Click the **`index.html`** file in the file list
3. On the file page, click the **download icon** (⬇) in the top right corner
4. Save it somewhere permanent on your computer — for example `E:\Icarus\BreedingTracker\index.html`

> Avoid saving it to a cloud-synced folder like OneDrive or Google Drive, as file syncing can occasionally conflict with the auto-save. A local drive is ideal.

### Option B — Clone the repository

If you use Git, you can clone the repo and pull updates as they're released:

```
git clone https://github.com/rnksekmeth/icarus-breeding-tracker.git
```

---

## First Launch

1. Open `index.html` in Chrome or Edge
2. A startup screen will appear asking where to save your data
3. Click **✨ Start fresh (create new file)**
4. A save dialog will open — navigate to the same folder as `index.html` and save as `herd_data.json`
5. The app is now ready to use

On every future launch, the app will remember your file. Click **▶ Continue with herd_data.json** and grant permission when the browser asks — this is a one-click step each session.

### If you already have data from a previous version

If you used an earlier version of the app that stored data in the browser, click **⬆ Migrate data from browser storage** on the startup screen. This will read your existing data and save it to the new file format, then clear the old browser storage.

---

## Saving

The app saves automatically after every change. A small **💾 Saved** indicator appears briefly in the top right corner to confirm each save. You do not need to manually save.

Your data file (`herd_data.json`) can be backed up, copied to another computer, or shared with other players just like any regular file.

---

## How to Use

### Adding an Animal

Go to the **➕ New Animal** tab. Fill in the species, sex, bloodline, stats, and optionally the parents and phenotype. The app will generate a name automatically in the format `DR01 48F-Wild P3 VIG2`. Click **Add to Herd**.

### My Herd

The **📋 My Herd** tab shows all your animals. You can filter by species and status, and show or hide dead/culled animals with the **🪦 Show Dead** toggle. Each animal has a status you can set: Keep, Breed, Temp, Reserve, Discard, or Dead.

### Pairs & Breeding Advice

The **🔀 Pairs** tab lets you set up breeding pairs. Select a male and female and the app will show breeding advice — which stats can be improved and which animals to retire.

### Goals

The **⚙ Goals** tab lets you set target stats per species and configure which stat to breed out (removed from the total score).

### Lineage

The **🧬 Lineage** tab shows the family tree for any animal in your herd.

---

## Species Reference

| Species | Code | Notes |
|---|---|---|
| Dune Raptor | DR | |
| Swamp Raptor | SR | |
| Moa | BM | Base Moa |
| Slinker | SL | |

---

## Sharing the App

You can share the `index.html` file directly with other players — it is completely self-contained. They follow the same first launch steps above to set up their own data file.

The app is also accessible online at:
**https://rnksekmeth.github.io/icarus-breeding-tracker**

Note that when using the online version, the File System Access API still works — you will be prompted to pick a save location as normal.
