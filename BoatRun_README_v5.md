# BoatRun — User Guide

Four companion web apps: live recording, squad coaching, live spectating, and post-session analysis.

-----

## Contents

1. [Quick Start](#1-quick-start)
1. [Getting Started — Four Apps](#2-getting-started--four-apps)
1. [Metrics App](#metrics-app)
   - Setup · Screens · Layouts · Workouts · Recording
1. [Analyser App](#analyser-app)
   - Overview · Chart · Curves · Multi-session · Map & Export · Benchmark
1. [Coach App](#coach-app)
1. [Viewer App](#viewer-app)
1. [Metrics Reference](#metrics-reference)
1. [Google Drive Sync](#google-drive-sync)
1. [Limitations and Warnings](#limitations-and-warnings)
1. [Troubleshooting](#troubleshooting)

-----

## 1. Quick Start

Everything you need to be recording in under five minutes.

### Install on iPhone

1. **Settings → Privacy & Security → Location Services → Safari Websites** → Allow While Using the App → turn on Precise Location
1. Open the Metrics URL in Safari
1. **Share → Add to Home Screen**
1. Open the app from the home screen — tap **Allow Motion** when prompted

### Install on Android

1. Open the Metrics URL in Chrome
1. Browser menu **⋮ → Install App**
1. Allow location when prompted

### First session

1. Put the phone in the mount — flat, screen up, long axis along the boat, facing the stern
1. Boat still — tap **Calibrate** (8 seconds)
1. Tap **Start**, begin rowing — axis pill turns green within a few strokes

### Common first-use issues

| Symptom | Fix |
|---|---|
| Axis pill stays orange | Run calibration with phone in mount, boat still |
| Motion permission not asked | iOS Settings → Safari → Motion & Orientation Access → Allow |
| GPS red pill (poor accuracy) | Check location is Precise, not approximate |
| Session not uploading | Tap ☁ Drive button and sign in |
| Pace high/low in current | Expected — GPS pace is over-ground; use IMU metrics for technique |
| App won't install on Android | Use Chrome — other browsers don't support PWA install |

-----

## 2. Getting Started — Four Apps

| App | Install | Use on | Purpose |
|---|---|---|---|
| **Metrics** | Add to Home Screen | Phone in boat | Live recording |
| **Coach** | Add to Home Screen | Coach's phone or tablet | Live squad monitoring and workout control |
| **Viewer** | Bookmark only | Any browser | Watch the squad live — map + pace cards |
| **Analyser** | Bookmark only | Desktop or iPad | Post-session review and comparison |

Sessions recorded in Metrics are saved to local storage and optionally synced to Google Drive. The Analyser reads Drive files or accepts exported `.json` files.

The Coach and Viewer apps share a **squad code**. The coach generates it, rowers enter it in Metrics settings, spectators enter it in the Viewer.

-----

---

# Metrics App

---

## Setup

### First launch

Tap **Allow Motion** and **Allow Location** when prompted. Both are required.

If permissions are denied: iOS Settings → Safari → Motion & Orientation Access → Allow. For location: Settings → Privacy & Security → Location Services → Safari Websites → Allow While Using the App → Precise Location on.

### Calibration

Before your first session and whenever you reposition the phone:

1. Phone in mount, boat completely still
1. Tap **Calibrate** — runs for 8 seconds
1. Jerk and acceleration thresholds are computed and saved — the status pill turns green

Recalibrate when you change mounting position, switch boats, or if stroke detection feels sluggish or triggering falsely.

### Mounting

- Flat in the boat, screen up, long axis roughly aligned with the boat axis
- Closest to the rigger gives the strongest stroke signal
- **Facing the stern** (opposite to direction of travel) — the app accounts for this

### Squad code (for Coach integration)

Enter the code your coach provides in **HOME → SETTINGS → Squad Code**. The coach generates the code in their Coach app settings.

-----

## Screens

### 🚣 LIVE

Main display during a session. A tile grid of chosen metrics updates in real time. Tap any tile to see a brief explanation.

Status pills in the top bar:

- **WAIT** — not rowing
- **AX:X** orange — axis detected, not locked
- **AX:X** green — axis locked, stroke detection active
- GPS accuracy pill — orange above 8m, red above 25m (pace suppressed when red)

### 📈 CURVE

IMU acceleration curve catch-to-catch. Last stroke (blue) and 5-stroke rolling average (orange) overlaid. Vertical dashed line = drive/recovery boundary. Green fill above zero, red below.

Four configurable tiles below the curve — tap any to cycle.

### 🏁 INTERVALS

When a workout is loaded: interval sequence, countdown, lap splits, and per-interval metrics.

### 🏠 HOME

- **LOG** — saved sessions; tap any to see summary, lap table, and workout breakdown
- **LAYOUTS** — display profiles
- **WORKOUTS** — build and manage workouts
- **HR ZONES** — zone configuration
- **SETTINGS** — boat class, pace unit, distance unit, squad code, and other options

-----

## Layouts and Tiles

### Layout profiles

A profile defines how many tiles appear and which metric each shows, with separate configurations for portrait and landscape.

**Built-in profiles**

| Profile | Portrait | Landscape |
|---|---|---|
| Race | 2×3 (pace, rate, oar arc, impulse, workout, selectable) | 2×2 (pace, rate, oar arc, workout) |
| Training | 2×4 (pace, rate, dps, catch dur, oar arc, impulse, workout, selectable) | 3×3 (pace, rate, dps, impulse, catch dur, run loss, oar arc, workout, selectable) |

Tap a profile name to activate it. Tap **+ NEW PROFILE** to create a custom one — choose grid size for each orientation, then tap each tile slot to assign a metric.

### Assignable metrics

| Key | Metric | Colour |
|---|---|---|
| `pace` | Pace /500m | 🔴 |
| `rate` | Stroke Rate | 🟢 |
| `dps` | Dist / Stroke | 🔴 |
| `catch` | Catch Slope | 🔵 |
| `impulse` | Impulse | 🔵 |
| `runloss` | Run Loss | 🔵 |
| `ratio` | Stroke Ratio | 🟢 |
| `char` | Stroke Char % | 🟢 |
| `oarangle` | Oar Arc | 🔴 |
| `checkdelta` | Check Delta | 🔵 |
| `catchdur` | Catch Duration | 🔵 |
| `selectable` | Selectable tile | — |
| `workout` | Workout countdown | — |
| `empty` | Blank | — |

**Selectable tile**: cycles through Time of Day, Total Time, Lap Time, Total Distance, Lap Distance, Avg Pace, and Lap Pace. Tap the tile during a session to cycle to the next option.

**Oar Arc tile**: tap on the live screen to flip between Scull (outboard 2.0m) and Sweep (outboard 2.6m). A toast confirms the current setting. This is the only way to change the boat class — there is no setting in the Settings panel for outboard length.

### Curve tab tiles

Tap any of the four tiles below the curve to cycle through:

- Stroke Rate
- Catch Slope
- DPS
- Catch Duration
- Impulse
- Run Loss
- Char %
- Stroke Ratio
- Check Δ
- Oar Angle
- Pace
- Workout

Default: Stroke Rate · Catch Slope · DPS · Catch Duration.

-----

## Workouts

### What workouts do

A structured sequence of steps — warmup, work intervals, rest, cooldown. When loaded:

- INTERVALS tab counts down each step
- The `workout` tile shows current step and time remaining
- At step end, metrics are captured (pace, rate, catch, impulse, char, ratio, run loss, arc, consistency, catch duration, averaged IMU curve)
- All interval data saved with the session; available for benchmark comparison in the Analyser

### Loading a workout

HOME → WORKOUTS → tap the workout → INTERVALS tab becomes active → start your session normally.

### Built-in workouts

| Workout | Structure |
|---|---|
| **Race 1000m** | Warmup (open) → 1000m work (starts when rowing) → Cooldown (open) |
| **Baseline: Rate Ladder** | Warmup (open) → 4 repeats of [1min @24, 1min @26, 1min @28, 1min @30, 4min rest] → Cooldown (open) |

The last rest in each repeat is skipped.

### Baseline: Rate Ladder

The primary repeatable test for tracking fitness and technique.

| Rep | Steps | Rest after |
|---|---|---|
| 1–4 | 4 × 1 min at 24 / 26 / 28 / 30 spm | 4 min (skipped after rep 4) |

Do the test on the same stretch of water in the same direction each time for valid pace comparisons.

**What to compare across sessions using Analyser Benchmark:**

- 🟢 Rate, char %, ratio, oar arc — compare freely across any conditions
- 🔵 Catch slope, impulse, consistency, check delta, catch duration — compare within the same boat
- 🔴 Pace, DPS — only if conditions and direction are matched

### Building a custom workout

HOME → WORKOUTS → **+ NEW WORKOUT** → name it → add steps:

- **Warmup / Cooldown** — ends when you tap Lap
- **Work** — set duration (time or distance)
- **Rest** — set duration

Select two or more adjacent steps and tap **Group as Repeats** to create a repeat group. Set the repeat count.

**Step modes:** Time, Distance, or Open (runs until Lap is tapped).

**▶| Start when rowing**: holds the countdown until the boat is actually moving. Tick on work or rest steps. Useful for rolling starts.

-----

## Recording a Session

### Starting

Tap **Start**. Optionally load a workout first from HOME → WORKOUTS. Begin rowing — stroke detection activates within the first few strokes.

### Laps

Tap **Lap** to record a split. Each lap records distance, time, pace, rate, catch, DPS, impulse, run loss, arc, and check delta.

**Lap while stopped**: tapping Lap while the boat is not moving pauses the lap timer. The timer resumes automatically when the boat starts moving again. Useful for marking the end of a rest interval without accumulating stationary time in the lap.

If a workout is loaded, Lap advances through steps: warmup/cooldown end on Lap; work and rest steps advance automatically on time or distance.

### Pausing and finishing

Tap **Stop** to pause, **Resume** to continue. Tap **Finish Session** to end — session saved to local storage and queued for Drive upload.

If the app closes mid-session, the 30-second autosave is recovered automatically on next open.

### Reviewing on device

HOME → LOG → tap the session: summary stats, workout interval breakdown, lap splits table.

### Deleting a session

In HOME → LOG, swipe a session row or tap the delete icon to remove it from local storage. This removes the local copy only — if the session has already synced to Drive, the Drive copy is unaffected. Delete from Drive in the Analyser.

-----

---

# Analyser App

---

## Overview

Desktop-first tool for post-session analysis. Open in a browser on a laptop or tablet.

### Loading a session

**From Drive:** Sign in at the start screen, then click any session in the list.

**From file:** Click **📂 Open file** and select a `.json` session file, or drag and drop onto the start screen.

**Adding more sessions:** Once a session is loaded, use **☰ Files → ＋ Add file** or **☰ Files → ☁ Add from Drive** to load additional sessions for comparison. Each gets its own tab.

### Summary cards

Cards appear at the top in this order:

Distance · Duration · Pace · Rate · DPS · Check Delta · Run Loss · Oar Arc · Impulse · Catch Slope · Ratio · Stroke Char · Catch Duration · HR (if recorded)

Each card is colour-coded by category (🔴 condition-dependent, 🔵 boat-dependent, 🟢 independent). Click any card to toggle that metric series on or off in the main chart.

### Interface controls

**Theme:** Light/Dark toggle in the top bar.

**Units bar:** Appears when a session is loaded.

- **Boat class:** Scull or Sweep — affects oar arc display
- **Pace:** /500m, /1km, km/h, /mi, mph
- **Dist:** km or mi
- **Sub:** m, ft, in (DPS sub-unit)

All units apply immediately across charts, cards, and tables.

-----

## Chart and Navigation

### Main chart

Stroke metrics plotted over the session. Each series is colour-coded:

| Series | Colour |
|---|---|
| Pace | Green |
| Rate | Yellow |
| DPS | Purple |
| Check Delta | Steel blue |
| Run Loss | Blue |
| Oar Arc | Teal |
| Impulse | Pink |
| Catch Slope | Red |
| Ratio | Blue-grey |
| Stroke Char | Orange |
| Catch Duration | Lavender |

Click any legend label or summary card to hide/show that series. X-axis: stroke number, distance, or time. EMA smoothing: off or 3/5/10/15/20/30 strokes.

### Overview strip

Miniature full-session view below the chart. Drag the window to pan; drag its edges to zoom.

### Tooltip

Hover or tap the chart for all metric values at the nearest stroke.

### Lap markers and laps table

Lap boundaries appear as vertical dashed lines. **Click any lap row** to zoom the chart to that lap and create a selection covering all its strokes. The selection bar then appears above the chart — click **＋ Add to curves** to pin as a curve group.

### Stroke data table

Every stroke with all metrics. Click a column header to sort. **Click any stroke row** to pin that stroke — a highlight appears on the chart and a white circle marker shows its GPS position on the map. Click the same row again to unpin.

### Selecting a range

Drag on the main chart to select strokes. The bar above the chart shows averages and offers **＋ Add to curves** and **✕ Clear**.

-----

## Curve Analysis

### Adding a curve group

Three ways:

1. Drag a selection on the chart → **＋ Add to curves**
1. Click a lap row → selection is set automatically → **＋ Add to curves**
1. Drag an existing group band on the overview strip to reposition or resize it

Up to 8 groups. Click **×** on a chip to remove one, **Clear all** to remove all.

### Curve canvas

Averaged catch-to-catch IMU curves overlaid, time-normalised so drive phases align. Below: integrated speed profile.

### Curve stats table

One column per group:

| Row | Description |
|---|---|
| Strokes | Total strokes in this group |
| w/ curves | Strokes that contain IMU curve data |
| Time | Elapsed time across the group |
| Avg Pace | |
| Best Pace | |
| Avg Rate | |
| Avg DPS | |
| Avg Check Delta | |
| Avg Run Loss | |
| Avg Oar Arc | |
| Avg Impulse | |
| Avg Catch Slope | |
| Avg Ratio | |
| Avg Stroke Char | |
| Avg Catch Duration | |

-----

## Multi-session Comparison

Once the first session is loaded, add more via **☰ Files → ＋ Add file** or **☰ Files → ☁ Add from Drive**. Each session gets a tab — click a tab to make it active.

To compare curves across sessions:

1. Make the first session active, select strokes, click **＋ Add to curves**
1. Switch to the second session tab, select strokes, click **＋ Add to curves**
1. Groups from both sessions appear on the curve canvas together — each chip shows its session name

The IMU curve shape is not affected by wind, tide, or current — cross-session curve comparison is always valid regardless of conditions on the two days.

What to compare:

- Curve shape — most reliable indicator of changed mechanics
- 🟢 Rate, char %, ratio — any conditions
- 🔵 Catch slope, impulse, check delta, catch duration — same boat only
- 🔴 Pace, DPS — same stretch, direction, conditions only

-----

## Map, HR, and Export

### Route map

GPS track drawn as a blue line. Pinned curve groups show their GPS segment in the group's colour. A pinned stroke (clicked in the stroke table) shows as a white circle on the map at that GPS position.

### Heart rate chart

HR trace with zone band overlays, if recorded. Shares the time axis with the main chart.

### TCX export

**☰ Files → ⬇ Export TCX** — downloads a `.tcx` file for Garmin Connect or Strava manual upload.

### Deleting sessions from Drive

In the **☰ Files** menu, the Drive picker shows a 🗑 button next to each session. Click it to permanently delete that file from Google Drive. This does not affect the local copy in Metrics.

-----

## Workout Benchmark

When a session recorded with a named workout is loaded, a **Workout Benchmark** section appears below the chart.

One table per work interval, one column per session. Click **Compare via Drive ▾** to scan Drive for sessions recorded with the same workout and add them as comparison columns.

| Metric | Category |
|---|---|
| Pace | 🔴 |
| Rate spm | 🟢 |
| Catch slope | 🔵 |
| Impulse | 🔵 |
| Char % | 🟢 |
| Ratio | 🟢 |
| Run loss % | 🔵 |
| Oar arc ° | 🔴 |
| DPS | 🔴 |
| Consistency | 🔵 |
| Check Δ | 🔵 |
| Catch duration | 🔵 |

Below each rep table: averaged IMU curves overlaid — all sessions in their colours, current session thicker.

-----

---

# Coach App

---

Install on the coach's phone or tablet (Add to Home Screen, same as Metrics).

### Setup

SETTINGS tab → enter or generate a squad code → enter your name → **SAVE & CONNECT**. Share the code with rowers (they enter it in Metrics → HOME → SETTINGS → Squad Code).

Generate a fresh code each session to avoid accidentally sharing data with another crew using the same code.

### LIVE tab

**Squad map** — every connected rower as a dot, coach position shown separately. Tap a dot to open rower detail.

**Rower grid** — one tile per rower showing name, stroke rate (large), pace (large), and up to 13 configurable secondary metrics. A tile goes grey if no data for 8+ seconds.

Tap a tile to open **rower detail**: full metrics, 30-minute trend charts, mini route map.

**LAP — ALL BOATS** — sends a simultaneous lap command to all connected rowers.

### WORKOUTS tab

Build workouts with the same builder as Metrics. Tap a workout → **PUSH TO SQUAD** to load it on all connected rowers' Metrics apps.

### SETTINGS tab

- Squad code and coach name
- Toggle which secondary metrics appear on rower tiles: Dist, DPS, Ratio, Run Loss, Catch, Catch Dur, Impulse, Char %, Oar Angle, Check Δ, Strokes, Laps, Time

### Connectivity

CONNECTED (green) or OFFLINE in top bar. All devices need mobile data — Wi-Fi is not available on open water. Metrics broadcasts live data every 2 seconds while recording.

-----

---

# Viewer App

---

No install needed — just a browser link. For spectators and athletes waiting their turn.

### Joining

Open the Viewer URL → enter the squad code from your coach → **CONNECT**.

### What you see

**Map** — full-screen map with each rower as a coloured labelled dot, updating continuously.

**Rower strip** — scrollable bar along the bottom, one card per rower showing name, stroke rate, and pace. Cards go grey when data is stale.

### Leaving

Tap **✕ LEAVE** in the top bar.

-----

---

# Metrics Reference

---

Metrics are colour-coded by what influences them:

- 🟢 **Green** — condition and boat independent. Compare across any session, any conditions, any boat of the same class. Source: IMU timing only.
- 🔵 **Blue** — boat dependent. Heavier boats produce lower readings for the same force. Compare within the same boat only. Source: IMU acceleration.
- 🔴 **Red** — condition dependent. GPS-derived. Tide, current, and wind affect the reading. Compare in matched conditions only.

-----

### 🔴 Pace /500m

Boat speed expressed as time per 500m. Lower is faster.

GPS Doppler speed, 5-second sliding window. Suppressed when GPS accuracy > 25m or boat speed < 0.7 m/s.

**Use:** Set pace targets for intervals. Compare lap to lap within a session. Do not compare across sessions on tidal water unless conditions and direction are matched.

-----

### 🔴 Moving Pace

Pace averaged over periods when the boat is actually moving. Gives a more honest average for sessions with stationary intervals.

**Use:** Primary pace reference for interval training. Large gap between moving and average pace means significant time was spent stationary.

-----

### 🔴 Distance Per Stroke (DPS)

Boat distance per complete stroke cycle. GPS mean speed over the stroke period ÷ stroke rate. Typical single scull values: 7–11m depending on rate and conditions.

**Use:** At equal pace, higher DPS means achieving it at a lower rating — more efficient. A drop mid-session at steady rate often signals fatigue.

-----

### 🟢 Stroke Rate (spm)

Strokes per minute. Median of last 5 catch-to-catch intervals. Backed up by autocorrelation when the catch detector is stale.

**Use:** The control variable for structured training. Clears after a rest gap > 5s; reappears after 2 new catches.

-----

### 🟢 Stroke Ratio

Recovery time ÷ drive time, displayed as `1 : X`.

- 1 : 2.0–2.5 at training rates
- 1 : 1.5–1.8 at race rates
- Below 1 : 1.8 — rushed recovery

**Use:** Clearest indicator of a hurried stroke. If ratio drops as rate increases, the rower is shortening the recovery rather than quickening the drive.

-----

### 🟢 Stroke Characteristic (Char %)

Where in the drive the peak acceleration occurs. 0% = at catch, 100% = at finish.

- 30–45% — front-loaded, preferred
- 50–60% — mid-drive, acceptable
- 65%+ — back-loaded, soft catch or late blade entry

**Use:** Rising char through a session indicates the catch is deteriorating under fatigue. Pair with catch slope: high slope + low char = clean front-end loading.

-----

### 🔴 Oar Arc (degrees)

Angle swept by the oar during the drive, derived from GPS drive distance and the configured outboard. A 10% blade slip allowance is applied.

Outboard is fixed at **2.0m for scull and 2.6m for sweep**. Tap the Oar Arc tile on the live screen to toggle between boat classes — a toast confirms the current setting.

Typical values: 85–110° depending on rigging and boat class.

**Use:** Consistent arc across strokes = full, repeatable drive length. Note: arc is GPS-derived and condition-dependent — a following current inflates the reading, a head current deflates it, even if actual oar arc is unchanged. Compare arc within a single direction of travel, not between laps on a tidal course.

-----

### 🔵 Catch Slope (m/s³)

How quickly the blade loads at the catch — the peak rate of change of acceleration at catch entry. Higher = more aggressive, faster loading.

Two values: rolling 8-stroke average (Catch) and session maximum (Peak).

**Use:** Rising catch slope as rate increases = adapting well. Falling = catch sacrificed for cadence. Large gap between avg and peak = can produce a clean catch but not sustain it. Not comparable across boat classes.

-----

### 🔵 Catch Consistency (m/s³ stdev)

Standard deviation of recent catch slope values. Lower = more repeatable catches.

**Use:** Target below 20% (below 10% for experienced scullers). Consistency worsening late in a session is an early fatigue indicator — usually appears before pace drops.

-----

### 🔵 Catch Duration (ms)

Time from the deceleration spike at blade entry until drive force builds. Shorter = quicker, more direct connection.

**Use:** A long catch duration means the blade is in the water but not yet loaded — a pause, slack, or hesitation. High catch slope + long duration = aggressive entry not converting immediately to drive force.

-----

### 🔵 Drive Impulse

Total positive acceleration delivered to the hull during the drive — integral of the accelerometer signal over the drive phase. Expressed as Δv (m/s). Not comparable across boat classes.

**Use:** Condition-independent measure of how hard the boat was pushed. Impulse rising at constant pace = increasing effort for the same result. Impulse falling at improving pace = increasing efficiency.

-----

### 🔵 Run Loss

How much the boat slows during recovery — velocity drop measured by integrating accelerometer data over a 2-second post-drive window.

Shown as percentage of stroke velocity swing (self-normalising).

- Below 15% — good for sculling
- Above 25% — something is disrupting the run (check, poor balance, rough water)

**Use:** High impulse + high run loss = energy wasted in deceleration, often from too low a rating for the force applied. Low impulse + low run loss = efficient, consistent drive.

-----

### 🔵 Check Delta (m/s)

Total speed swing within a stroke cycle — maximum minus minimum boat velocity, catch to catch. Lower = smoother run.

**Use:** High check delta = the boat is accelerating and decelerating sharply, wasting energy overcoming inertia. Compare with run loss: high check delta + low run loss often points to a jerky drive rather than a disrupted recovery.

-----

---

# Google Drive Sync

---

Sessions sync to a private app folder in your Google Drive (not visible in the regular Drive interface).

### Signing in

Tap the **☁ Drive** button in Metrics or Analyser. A sign-in popup opens.

### How sync works

- Uploaded automatically when a session finishes, if signed in and connected
- Failed uploads queue and retry automatically on next app open with connection
- HOME → LOG shows a **synced** badge for confirmed Drive sessions

### Loading sessions in the Analyser

Sign in at the start screen → sessions listed by date with distance, duration, avg pace, and stroke count.

### Deleting sessions

**In Metrics (local only):** HOME → LOG → swipe or tap the delete icon on a session. Removes local copy only. Drive copy is unaffected.

**In the Analyser (Drive/cloud):** When the Drive picker is open, tap the 🗑 button next to any session to permanently delete it from Google Drive.

### Benchmark comparison via Drive

**Compare via Drive ▾** in the Benchmark section scans every Drive session for matching workouts. A large library may take 20–30 seconds. Progress shown in the button.

-----

---

# Limitations and Warnings

---

### GPS metrics are over-ground, not through-water

All GPS-derived metrics — pace, DPS, and oar arc — measure motion relative to the ground, not through the water. On tidal rivers:

- A 0.3 m/s following current improves displayed pace by roughly 10 seconds per 500m at a 2:00 baseline
- Oar arc reads high with a following current and low into a head current
- DPS is inflated downstream and deflated upstream for the same reason

IMU-derived metrics — stroke rate, stroke ratio, char %, catch slope, impulse, run loss, check delta, catch duration — are not affected by current. These are the reliable technique metrics on tidal water.

### Phone mounting is critical for all IMU metrics

All IMU metrics assume the phone is rigidly fixed to the hull. Any movement between phone and boat corrupts every IMU-derived metric. A loose mount that rocks at a frequency near the stroke rate can corrupt stroke ratio and char %. Recalibrate whenever you reposition the phone.

### Axis detection after a rest gap

Axis lock can degrade after a long rest. The pill turns orange when unlocked. If detection resumes but the pill stays orange after several strokes, row steadily for 20–30 strokes to allow the detector to relock.

### Multi-rower boats

In doubles, quads, and eights, the accelerometer signal is a superposition of all rowers' catches. Stroke detection follows the dominant signal (usually the stroke seat). At high rates in crew boats, adjacent catches can trigger false detections. Catch slope and impulse values are not comparable with single-scull values.

### No absolute force measurement

IMU metrics measure the hull's acceleration response to blade force, not the force itself. The same blade force produces different accelerations in a single scull vs. a crew boat. Do not compare catch slope, impulse, or run loss across boat classes.

### Temperature and battery

Cold water (below 5°C) can cause the phone to throttle CPU or reduce sensor polling rates. Keep the phone warm before launching. For sessions over 90 minutes, start with a full charge. A battery case is recommended for two-a-day days.

### Coach and Viewer require mobile data on water

All devices need an active mobile data connection. Metrics continues recording locally regardless of connectivity — the Coach live view is best-effort. Rower tiles go grey (data gap > 8s) in areas with poor signal.

### Session data safety

Local storage can be cleared by the browser if the device runs critically low on storage. To protect data:

- Export sessions as JSON from HOME → LOG → session → Export immediately after a significant session
- Do not close the browser tab mid-session without tapping Finish
- Confirm the synced badge appears before relying on Drive as your only copy

### Strava integration

Strava OAuth and TCX auto-upload are coded and ready in Metrics but not yet activated — Strava requires a paid API tier before approving the app. In the meantime, export a TCX file from the Analyser and upload manually: Strava → Manual Upload → select the `.tcx` → activity type Rowing.

### Oar arc is a geometric approximation

The formula computes the chord angle — the angle subtended by the straight-line GPS displacement during the drive. For arcs below 120° the error is less than 2%. The 10% blade slip correction is a fixed estimate; actual slip varies with blade design and rowing style.

-----

## Troubleshooting

**Stroke detection not triggering**

- Run calibration with the phone in the mount and the boat still
- If the axis pill stays orange for more than a minute, the stroke signal is too weak on all axes
- Ensure the phone is mounted firmly

**Pace showing high — or dropping out mid-session**

- GPS accuracy must be better than 25m
- Under bridges or near tall buildings, GPS can drop out temporarily
- In tidal water, pace shows over-ground speed — this is expected

**Session not saving**

- A failed save shows a warning toast. The autosave (every 30 seconds) is recovered on next open.

**Drive sync failing**

- Check you are signed into Drive (☁ button)
- Pending sessions retry automatically on reconnect
- Export as JSON from the session detail view as a backup if upload keeps failing

**Axis not locking**

- The pill turns green after ~4 strokes with consistent signal
- Row with deliberate catch movements for the first few strokes to help the detector

**No rowers appearing in Coach**

- Check all phones have mobile data (not just Wi-Fi)
- Confirm the squad code matches exactly
- Coach top bar shows CONNECTED (green) when the Firebase link is live

**Rower tiles going grey in Coach**

- No data received in the last 8 seconds
- Check the rower's Metrics app is recording (not paused)
- Intermittent grey is normal under bridges or in poor signal areas

**Session loads in Analyser but chart is empty**

- All series may be toggled off — click any legend label or summary card to restore
- Zoom out using the − button or drag the overview window edges

**TCX export not appearing on Strava**

- On Strava: Manual Upload → select the `.tcx` → set activity type to Rowing
- GPS data must be present — sessions recorded without location permission will not produce a valid TCX track
