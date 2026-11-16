# 💧 AquaGuard: SDG 6 Water Safety Toolkit

**Author:** Alexandru Arhirii
**Goal:** UN Sustainable Development Goal 6, Clean Water and Sanitation

AquaGuard is a free, offline-friendly web app with three tools:

| Tool | What it does | SDG target |
|---|---|---|
| 🧪 Water Test | Checks pH, turbidity, TDS and free chlorine against WHO guideline values and gives a safe / treat / do-not-drink verdict | 6.1 |
| 🚿 Usage Tracker | Tracks daily water use against a 100 L goal with saving tips | 6.4 |
| 🧼 Sanitation Checklist | Daily hygiene habits with a score | 6.2 |

## Run it
Open `index.html` in any browser. No install, no internet, no server.

## Thresholds used
| Parameter | Good | Warning | Unsafe |
|---|---|---|---|
| pH | 6.5-8.5 | n/a | outside range |
| Turbidity (NTU) | ≤1 | 1-5 | >5 |
| TDS (mg/L) | ≤600 | 600-1000 | >1000 |
| Free chlorine (mg/L) | 0.2-5 | <0.2 | >5 |

Source: WHO Guidelines for Drinking-water Quality. This is a screening tool, **not** a lab test.

## How it works
- Pure HTML, CSS and JavaScript in one file.
- Each reading is checked by a rule; the worst result decides the overall verdict.
- Usage and checklist data are saved in the browser's `localStorage` (no accounts, no data leaves the device).
- Responsive layout with automatic dark mode.

## Test cases
| Input | Expected |
|---|---|
| pH 7, turbidity 0.5, TDS 300, chlorine 0.5 | ✅ Safe |
| pH 7, turbidity 3 | ⚠️ Treat before drinking |
| pH 9 | ⛔ Do not drink untreated |
| Chlorine 0.1 | ⚠️ Warning |
| Empty form | "Enter at least one reading" |

## Limitations and future work
- Values are entered manually; next step is reading real sensors (ESP32/Arduino).
- Add Romanian and other languages, and community water-point maps.

## Responsible AI usage
See [AI_USAGE.md](AI_USAGE.md).

## License
MIT, © 2026 Alexandru Arhirii
