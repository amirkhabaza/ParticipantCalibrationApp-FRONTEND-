# Participant Calibration App

PsychoPy app for **9-point eye-tracker calibration** on the participant monitor. It shows fixation targets and logs **when** (VSYNC-aligned, Unix timestamps) and **where** each target appeared. Gaze is recorded separately by the eye tracker; this repo handles only the **stimulus + ground-truth log** side.

Built for NASA internship eye-tracking research.

---

## Quick start

**Prerequisites:** Python **3.10**, a monitor with OpenGL (standard on Mac / Windows laptops).

```bash
git clone https://github.com/amirkhabaza/ParticipantCalibrationApp-FRONTEND.git
cd ParticipantCalibrationApp-FRONTEND/Frontend
chmod +x run.sh          # macOS / Linux, first time only
./run.sh                 # creates .venv, installs deps, runs calibration
```

Windows (PowerShell):

```powershell
cd Frontend
.\run.ps1
```

**Smoke test without a participant** (skips instructions and exit prompt; auto-confirms each dim target after 0.3 s):

```bash
./run.sh --auto
```

**Output:** `Frontend/output/calibration_targets_<UTC-timestamp>.csv` (one file per run; see [Output CSV](#output-csv))

Full documentation: [Frontend/README.md](Frontend/README.md)

---

## Repo layout

```
ParticipantCalibrationApp-FRONTEND/
├── README.md                    ← This file (overview + quick start)
├── Backend/                     ← Calibration model (separate workstream; placeholder)
└── Frontend/
    ├── README.md                ← Full documentation
    ├── calibration_9point.py    ← Main application (~700 lines, single file)
    ├── requirements.txt         ← PsychoPy dependency
    ├── run.sh                   ← macOS/Linux: setup + run
    ├── run.ps1                  ← Windows: setup + run
    └── output/
        └── calibration_targets_<UTC-timestamp>.csv   ← Created after each run (gitignored)
```
