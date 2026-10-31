# drive-replay

> **Project Year: 2022**  
> Driving data replay dashboard with playback controls, speed, steering and telemetry visualisation.

An interactive driving data replay and Augmented Reality Head-Up Display (AR-HUD) dashboard. Replays vehicle telemetry, motion predictions, and dynamics traces recorded from real-world drive scenes.

---

## Key Features

- **Driving Data Replay**: Multi-channel playback controls (play, pause, scrub, step) synchronizing vehicle speed, yaw rate, steering angle, and IMU signals.
- **AR-HUD Motion Prediction**: Interactive Heads-Up Display demo (`hud.html`) projecting road-aligned trajectory predictions (`mpred.js`) and vehicle dynamics simulations (`vdyn.js`).
- **Telemetry Visualisation**: Real-time canvas rendering of multi-sensor timelines, error margins, and scene traces.
- **nuScenes Integration**: Benchmark scenarios derived from the nuScenes dataset with ground-truth trajectory comparison.

---

## Quick Start & Execution

### 1. Launch the Replay Dashboard
Serve the dashboard locally with any static web server:
```bash
# Using Node / npm
npm install
npm start
# Opens at http://localhost:3000

# Or using Python 3
python3 -m http.server 3000
```

Access the dashboards:
- Main Replay Dashboard: `http://localhost:3000/index.html`
- AR-HUD Prediction Demo: `http://localhost:3000/hud.html`

### 2. Python Backend & Tools
To process drive recordings and run offline evaluations:
```bash
pip install -r requirements.txt
python3 -m replay.run --config configs/default.yaml
```

---

## Repository Structure

```
.
├── index.html            # Main Driving Replay dashboard entry point
├── hud.html              # AR-HUD interactive motion prediction view
├── app.js                # Core dashboard visualization controller
├── hud.js                # HUD canvas rendering and overlay logic
├── mpred.js              # Client-side motion prediction model
├── vdyn.js               # Vehicle dynamics kinematic model
├── data/                 # Telemetry timelines, scene traces, and error plots
├── media/                # Video recordings and HUD loop previews
├── configs/              # Scenario and pipeline configurations
├── replay/               # Python replay engine and telemetry handlers
├── scripts/              # Utility scripts for data formatting
├── tools/                # Benchmarking and evaluation utilities
└── package.json          # Node server dependencies
```

---

## Data & Licensing Attributions

- **Code**: Licensed under the [MIT License](LICENSE).
- **Drive Data & Media**: Driving traces and scenario recordings in `data/` and `media/` are derived from nuScenes v1.0-mini and the nuScenes CAN bus expansion and are licensed under [CC BY-NC-SA 4.0](https://www.nuscenes.org).
