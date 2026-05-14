# Controle de Ponto

Single-page HTML app for tracking Brazilian CLT work hours and lunch breaks.

**Zero dependencies.** Open `index.html` in any browser — works offline, on desktop and mobile.

## Features

- **Smart "Registrar" button** — one button advances through all four stages automatically:
  1. Entry → 2. Lunch start → 3. Lunch return → 4. Exit
- **Worked hours counter** — real-time counter showing hours worked:
  - Pauses during lunch
  - Shows overtime or deficit when exit is registered
- **Lunch timer** — two modes:
  - Lunch end set → countdown to end of lunch
  - Lunch start only → countdown to minimum return time
- **Smart exit calculation** — exit = entry + workload + lunch duration
  - Take 2h lunch → leave 1h later
- **CLT rules** built in (art. 71):
  - Workload > 6h → minimum 1h lunch
  - 4–6h workload → minimum 15min lunch
  - ≤ 4h workload → no mandatory lunch
- **App validations:**
  - Lunch duration ≥ CLT minimum
  - ≥ 15min between entry and lunch start
  - Lunch ≥ 1h after entry
  - ≥ 1h of work remaining after lunch
- **Stats panel:** total shift, lunch duration, expected/real exit, effective work time
- Dark theme, responsive, mobile-first

## Usage

1. Open `index.html` in your browser
2. Fill in work **entry time** (e.g. 09:00) or tap **Registrar** to log current time
3. Select daily **workload** (default 8h)
4. Tap **Registrar** when heading to lunch — logs current time as lunch start
5. Tap **Registrar** again on return — logs lunch end
6. Tap **Registrar** at end of day — logs exit, shows real vs. expected worked time

You can also fill in times manually at any step.

## Examples

| Entry | Lunch | Duration | Workload | Exit |
|-------|-------|----------|----------|------|
| 09:00 | 12:00–13:00 | 1h | 8h | **18:00** |
| 09:00 | 12:00–14:00 | 2h | 8h | **19:00** |
| 09:00 | 12:00–12:40 | 40min | 6h | **15:40** |
| 13:00 | 17:00–18:00 | 1h | 8h | **22:00** |

## How it works

```
exit = entry + workload + lunch_duration
```

Lunch time does **not** count as worked time. Every extra minute at lunch extends the workday.

## Deploy

### Local
Just double-click `index.html`.

### GitHub Pages
Push to a repo and enable Pages — the app is client-side only.

## License

MIT
