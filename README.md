# utech-gaming-planner

> An interactive degree-progress tracker for UTech Jamaica **BSc Gaming (Game Development)** students.

![Planner Screenshot](screenshots/full-view.png)

---

## What It Does

Click any unlocked course to cycle its status: **Available → In Progress → Completed**.  
Prerequisite courses unlock automatically as you complete their dependencies.  
Credits and overall percentage update in real time.

**No account. No server. Nothing leaves your browser.**

---

## Features

| Feature | Detail |
|---|---|
| 🎮 Single track | BSc Gaming — Game Development major, 4 years, 8 semesters |
| 🔒 Prereq locking | Courses unlock only when dependencies are met (including "either/or" prereqs) |
| 🎚 Elective credits | Pick 3 or 4 credits for the SCIT Elective from a dropdown on its card |
| 📊 Live credit counter | Tracks earned vs. total credits; header % and sidebar agree |
| 💾 Offline-first | All data in `localStorage` — works without internet |
| 📤 Export / Import | JSON backup so you can move data between devices |
| 🔐 XSS-safe | All output escaped; no user data ever hits a server |

---

## Screenshots

> _Placeholders — drop the images into `screenshots/` with these names._

| View | Description |
|---|---|
| ![Full planner](screenshots/full-view.png) | Years 1 and 2 of the full 4-year plan |
| ![Prereqs locking](screenshots/prereq-lock.png) | Locked courses with tooltip showing missing prereqs |
| ![Credits progress](screenshots/credits-sidebar.png) | Sidebar credits counter updating after completions |
| ![Elective credits](screenshots/elective-credits.png) | Choosing 3 or 4 credits for the SCIT Elective |
| ![Years 3-4](screenshots/years-3-4.png) | Years 3 and 4 — the Game Development major |

---

## How to Use

1. **Open** `index.html` in any browser — no install needed.
2. **Click a course** to mark it In Progress, then Completed.
3. **Set elective credits** using the dropdown on the SCIT Elective card.
4. **Export** your progress via the sidebar to back it up or move to another device.

---

## Local Development

```bash
git clone https://github.com/YOUR_USERNAME/utech-gaming-planner.git
cd utech-gaming-planner
# Open index.html in your browser — that's it.
```

No build step. No dependencies. Pure HTML/CSS/JS.

---

## Project Structure

```
utech-gaming-planner/
├── index.html          # Entire app — single file
├── screenshots/        # README screenshots
│   ├── full-view.png
│   ├── prereq-lock.png
│   ├── credits-sidebar.png
│   ├── elective-credits.png
│   └── years-3-4.png
└── README.md
```

---

## Curriculum Data

Course data is sourced from the official **UTech Jamaica SCIT Module Selection Guide — BSc Gaming, Majors: Game Design / Game Development** (revised March 2026). This planner covers the **Game Development** major.

| Year | Semesters | Credits |
|---|---|---|
| 1 — Foundations | 1, 2 | 36 |
| 2 — Core Computing | 3, 4 | 35 |
| 3 — Game Development Major | 5, 6 | 33 |
| 4 — Game Development Major | 7, 8 | 27 |
| **Total** | | **131** (132 with a 4-credit SCIT Elective) |

Notes on how the guide is modelled:
- **PRJ4020 Major Project** runs across Semester 7 and Semester 8; it appears as two cards, Part 1 and Part 2. The guide leaves its credits blank, so it uses 0 + 3 as on the other SCIT diet sheets.
- **CIT3003 Analysis of Algorithms** requires CMP2006 **and** either MAT2003 **or** MAT1008.
- **COM1024**'s requirement (COM1001 / CSEC / CAPE grade) is an entry requirement, so it is shown but never locks the course.
- **Animation Tools II** is printed as "ANI1002" in Semester 6; it is recorded here as **ANI1006** (its code in the Animation programme), with ANI1002 Animation Tools I as its prerequisite.
- **ECS3003** is printed "Server-side Devlopment"; the typo is corrected.
- Year labels are the planner's own; the guide only numbers the semesters.

---

## Security Notes

- All HTML output is escaped with a custom `esc()` function; tooltips are built with `textContent`.
- No inline event handlers are built from data — clicks are handled by delegated listeners.
- `localStorage` reads are validated — only known course IDs and status values are accepted.
- No external API calls. CSP meta tag blocks external script injection.
- Student info has `<` and `>` stripped and is capped at 200 characters before storage.
- Storage keys are prefixed `gam_` so this planner never clashes with other UTech planners on the same site.

---

## Contributing

Found a course discrepancy? Open an issue or pull request.  
Contributions welcome — especially if UTech updates the programme structure.

---

## License

MIT — free to use, share, and modify.

---

*Built for UTech Jamaica Gaming students. Not an official UTech product.*
