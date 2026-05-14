# Changelog

All notable changes to this project will be documented in this file.

## [Unreleased]

### Added
- localStorage persistence — daily state saved by ISO date, auto-expires next day, survives page refresh
- CLT compliance warning: worked hours exceeding 10h daily limit (art. 59)
- CLT compliance warning: exit after 22:00 triggers night-hours alert with 20% adicional notice (art. 73)
- CLT compliance warning: exit after 20:00 shows minimum next-day entry time based on 12h mandatory rest (art. 66)

### Changed
- Warnings refactored to `{msg, type}` objects — supports `error` (red) and `orange` severity levels

## [0.2.0] — 2026-05-14

### Changed
- Register button styled with gradient (`--accent` → `#5a7ae8`) and hover lift effect

## [0.1.0] — 2026-05-13

### Added
- Initial release: single-file CLT work-hour tracker
- Smart Registrar button advancing through 4 stages: entry → lunch start → lunch return → exit
- Real-time worked-hours counter, pauses during lunch
- Lunch countdown timer (to minimum return or to lunch end)
- Smart exit calculation: `exit = entry + workload + lunch duration`
- CLT art. 71 lunch minimums enforced (>6h workload → 1h min, 4–6h → 15min, ≤4h → none)
- Validation warnings: lunch before entry, lunch < 15min gap from entry, lunch < CLT minimum, < 1h work after lunch
- Stats panel: total shift, lunch duration, expected/real exit, effective work time
- Dark theme, responsive, mobile-first layout
