# legged-robotics-lab Repository Restructure Plan

## Goal
Refactor `legged-robotics-lab` from a single large `README.md` index into a GitHub-friendly Markdown knowledge base with:
- long-term master lists for retrieval
- daily logs for new updates
- lightweight navigation from `README.md`

## Target Structure

```text
legged-robotics-lab/
├── README.md
├── papers.md
├── repos.md
├── labs.md
├── jobs.md
└── legged-daily/
    ├── YYYY-MM-DD.md
    └── ...
```

## File Roles

### README.md
Use as a lightweight navigation page only.
It should link to:
- `papers.md`
- `repos.md`
- `labs.md`
- `jobs.md`
- `legged-daily/`

It should no longer hold the full master database once the split files exist.

### papers.md
Long-term curated paper list.
Use for papers worth preserving for future retrieval.
Do not include daily-only importance scores.

### repos.md
Long-term curated repository list.
Use for tools, codebases, simulators, datasets, and other repositories worth preserving.
Do not include daily-only importance scores.

### labs.md
Long-term source-network list.
Track labs, professors, and adjacent researchers, including the discovery sources used to expand the network over time.

### jobs.md
Dynamic jobs and opportunities list.
Keep active and recent academic or industry opportunities relevant to legged robotics.
Remove expired opportunities instead of preserving everything permanently.

### legged-daily/YYYY-MM-DD.md
Daily update log for a specific date.
Use for newly discovered papers, repos, lab signals, and job signals.
Do not include master-list planning inside the daily Markdown file.

## Migration Mapping From Current README.md

### Move to repos.md
Current sections such as:
- Websites
- Robotics (Kinematics, Dynamics, TO)
- Simulator & Models
- Dataset & Models
- Motion Generation, Retargeting, Editing
- RL
- MPC

### Move to labs.md
Current sections such as:
- Researchers (by Region)
- professor, lab, and research-group entries

### Keep out of README.md
The large tables and detailed profiles currently living in `README.md` should move into the split files.

## Suggested Migration Order
1. Rewrite `README.md` into a navigation page.
2. Create `repos.md` and move project / repo sections there.
3. Create `labs.md` and move researcher / lab sections there.
4. Create empty or starter versions of `papers.md` and `jobs.md`.
5. Start writing new daily logs into `legged-daily/YYYY-MM-DD.md`.
6. Let future confirmed updates populate the master list files incrementally.

## Operating Rules For Future Updates
- Daily logs capture **new findings for that date**.
- Master lists capture **curated long-term information**.
- `papers.md` and `repos.md` should stay readable in GitHub Markdown preview.
- `jobs.md` should remain dynamic and remove stale opportunities.
- `labs.md` should function as a growing source network, not just a static lab directory.

## Notes For GitHub Browsing
This structure is designed so the repository remains easy to read directly on GitHub:
- one file per major knowledge type
- readable Markdown rather than pure YAML
- daily logs separated by date
- lightweight top-level navigation
