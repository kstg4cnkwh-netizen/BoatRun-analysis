# BoatRun Privacy Policy

**Last updated:** 23 November 2026

BoatRun is a set of rowing performance apps (the BoatRun app for Row, Cox and Coach, the Viewer and the Analyser). This policy explains what data each app accesses, why, and where it goes.

## Data we collect and why

**Location (GPS)** — BoatRun uses your phone's GPS while recording a session to calculate boat speed, pace, distance and heading. Location data is used only during active recording and is stored in the session file you create.

**Motion & orientation sensors** — BoatRun uses the phone's accelerometer and gyroscope (DeviceMotion) to detect stroke timing, rowing technique metrics (catch quality, drive characteristics, recovery run, etc.) and boat heading. This data never leaves your device except as part of a session file you choose to save or sync.

**Heart rate** — if you connect a heart rate strap, import a watch file, or connect Apple Health or Health Connect, heart rate is saved with the session.

**Session details you add** — session names, notes, boat type and the race flag are saved with the session file.

**Daily check-in and training load** — if you use the daily check-in, BoatRun saves your sleep, soreness and energy scores and, if you enter or import them, resting heart rate and heart rate variability. These, and the training load BoatRun works out from your sessions, are saved on your device and in your own Google Drive (if linked). See *Health and fitness data* below.

**Location name and wind** — for on-water sessions, BoatRun looks up a general location name (for example "Hunter River, Newcastle") and the wind during the session. See *Location names and weather* below.

**Camera and microphone** — Coach can optionally record short videos of a rower's technique during a session. Video is saved locally on the coach's device as a file and is not uploaded automatically to any server.

**Session data (Firebase Realtime Database)** — While a squad session is active, live stroke rate, pace, position and rower name are sent to a Firebase Realtime Database so the Coach and Viewer apps can display them in real time. This data is transient — it reflects live session state and is not retained as a permanent log by us.

**Google Drive (App Data folder)** — If you link Google Drive, completed session files are saved to a hidden app-specific folder in your own Google Drive (`appDataFolder` scope). This folder is not visible in your normal Drive file list and cannot be accessed by other apps. Only you can access this data through your Google account.

**Account (optional)** — You can sign in with Google or Apple. BoatRun stores the account identifier returned by that provider along with your subscription tier, so Pro features unlock on any device you sign in to. BoatRun never creates or holds a password.

**Garmin training numbers (optional)** — if you connect Garmin, the training load, aerobic and anaerobic training effect and training effect label of your Garmin activities. See *Garmin Connect* below.

**Squad code** — Coach and Viewer use a short code you create or enter to link rowers, coaches, and spectators to the same live session. No account or personal identity is required to use this feature.

## Health and fitness data

- **Apple Health (iPhone) and Health Connect (Android)** — only if you tap Connect in the app's settings and allow access on the system permission screen.
  - **What BoatRun writes:** each saved session as a Rowing workout, with its start and end time, distance, heart rate and, for on-water sessions, the GPS route.
  - **What BoatRun reads:** resting heart rate, heart rate variability and sleep time for the last 14 days, used only to fill blank fields in your daily check-in.
  - BoatRun reads nothing else from Apple Health or Health Connect. It does not read your other workouts, and data read from them is not sent to BoatRun's servers.
- **Sharing with a coach** — off by default. If you turn on *Share training load with coach* for a squad, a summary is written to that squad in Firebase so its coach can see it. The summary contains:
  - your chosen name
  - your daily training load for the last 8 weeks, and your load ratio
  - daily session counts, distance and time
  - your last 14 daily check-ins
  - your next race

  Anyone with the squad's password can see it. Turning sharing off deletes it.
- **What BoatRun never does with health data:**
  - It is never used for advertising or marketing, never sold, and never given to data brokers.
  - It is never used for anything other than the training features described here.
  - It is never written to Apple Health or Health Connect without your permission.
- Garmin data is covered in *Garmin Connect* below.

## Location names and weather

- **Location name** — the session's start position, rounded to about 100 m, is sent through BoatRun's own server to **OpenStreetMap** (Nominatim), which returns the nearest river, lake or town. No name, account or other session data is sent with it. Results are cached for 30 days so the same spot is not looked up again. Location names © OpenStreetMap contributors, ODbL.
- **Wind** — a position from the session, rounded to about 100 m, and the session's date and time are sent to **Open-Meteo** to get the wind speed and direction for that hour. No other data is sent.
- Both lookups happen only for on-water sessions and only when the phone has a connection. If they fail, the session is saved without them.

## Strava, intervals.icu and Concept2 Logbook

- **Strava** — if you choose to connect Strava, BoatRun requests permission to upload activities on your behalf. A session (GPS track, heart rate if recorded, and rowing metrics) is uploaded to your Strava account only when you choose to export it. BoatRun does not read, store or analyse your existing Strava activities or profile beyond what's needed to complete the upload.
- **intervals.icu** (Pro) — if you paste your intervals.icu API key into the app:
  - **Uploads:** each saved session is uploaded to your intervals.icu account as an activity file (GPS track, heart rate, distance, laps, name and notes). You can turn automatic upload off and send sessions one at a time.
  - **Wellness:** BoatRun reads your intervals.icu wellness entries (resting heart rate, HRV, sleep quality, soreness and fatigue) for the last 14 days, only to fill blank fields in your daily check-in.
  - **Your key:** kept only on your device and sent only to intervals.icu.
- **Concept2 Logbook** (erg sessions, Pro) — if you choose to connect your Logbook, BoatRun asks Concept2 for permission to add workouts on your behalf. When an erg workout finishes, the name screen shows **Upload to C2 Logbook**; it is on by default once you have connected, and you can tap it to skip that workout. An upload contains the workout's date, time zone, time, distance, splits or intervals, stroke rate and count, drag factor, calories, heart rate (if recorded), stroke-by-stroke data, your Logbook weight class and the session name. The upload passes through BoatRun's own server on its way to Concept2. BoatRun uses this access only to add workouts to your Logbook.
- Access tokens and keys for Strava, intervals.icu and Concept2 are kept in the app on your device. Disconnecting in the app's settings removes them. Activities and workouts already uploaded stay in your Strava, intervals.icu or Logbook account and must be deleted there.

## Garmin Connect

If you choose to connect your Garmin account, BoatRun asks Garmin for permission to receive your activity data. We use it only to show Garmin's numbers beside the matching BoatRun session and in your training load and planning.

- **What is received** — for each Garmin activity: its start time, type, duration and distance, and Garmin's training load, aerobic training effect, anaerobic training effect and training effect label. If you send a planned workout to your watch, the workout's steps are sent to Garmin.
- **How it is used** — each activity is matched to the BoatRun session recorded at the same time (or the one you link by hand), and its numbers are saved with that session. They feed your training load chart, race planning and suggested workouts. If you join a squad and share with your coach, your coach can see them.
- **Where it goes** — Garmin sends activity data to BoatRun's own server (Cloudflare Workers), which also holds your Garmin access token. The matched numbers are kept in Firebase so your BoatRun apps can read them, and saved with your sessions on your device and in your own Google Drive app-data folder (if linked).
- BoatRun does not use Garmin data for advertising, does not sell it, and does not pass it to any analytics or AI provider.
- You can disconnect at any time from BoatRun's settings, or remove BoatRun in Garmin Connect. Disconnecting deletes your Garmin access token and the Garmin data held on BoatRun's server and in Firebase. Numbers already saved with your sessions stay with them until you clear them or delete the sessions.
- Garmin and Garmin Connect are trademarks of Garmin Ltd. or its subsidiaries.

## What we don't do

- We do not sell your data.
- We only pass data to the services listed in this policy, and only for the purposes described here.
- We do not use your data, including any health data, for advertising.
- We do not track you across other apps or websites, and the apps contain no analytics or tracking scripts.
- We do not require an account to record sessions in BoatRun, or to use Viewer or Analyser. An account is only needed to carry a Pro subscription across devices.

## Data storage and retention

Session data is stored locally on your device by default. If you enable Google Drive sync, session files are stored in your own Google Drive account under our control only insofar as our app writes/reads that folder — we do not have separate server-side copies. Live Firebase data used for Coach/Viewer sessions is not retained after the session ends. If you sign in, a single account record (identifier plus subscription tier) is retained in Firebase until you delete your account. A training load summary you share with a squad stays in Firebase until you turn sharing off. Location-name lookups are cached on BoatRun's server for 30 days against the rounded position only, with nothing that identifies you. Workouts written to Apple Health or Health Connect are stored there under Apple's or Google's control and can be deleted in the Health app or Health Connect.

## Deleting your account

You can delete your BoatRun account and its data at any time from within the app: **Metrics → Settings → Your Data → Account → Delete My Account**. You will be asked to confirm twice; the action is permanent and cannot be undone.

Account deletion permanently removes:

- Your BoatRun sign-in record (the linked Google or Apple account held by BoatRun)
- Your subscription tier / entitlement record in Firebase
- Your live squad membership entry, so you no longer appear on any coach's screen
- All BoatRun session files stored in your Google Drive app-data folder, if Drive is linked at the time of deletion
- Your Garmin connection, access token and any Garmin data held on BoatRun's server and in Firebase

Sessions saved locally on your device are not affected and can be deleted separately from the in-app session log. Purchase and billing records held by Apple or Google are retained by those companies under their own policies and for the period required by law; BoatRun cannot delete them. Deleting your account does not cancel an active subscription — cancel that in the App Store or Google Play subscriptions screen.

If you are unable to sign in, email support@boatrun.au from the address linked to your account and deletion will be carried out manually within 30 days.

## Third-party services used

- **Google Drive API** — for optional session backup/sync (your own Drive account)
- **Google Sign-In / Sign in with Apple** — for account sign-in and Drive authentication
- **RevenueCat** — subscription purchase and entitlement management on our behalf
- **Firebase Realtime Database (Google Cloud)** — for live squad coaching data during active sessions, the account record, and training load you choose to share with a squad
- **Cloudflare Workers** — BoatRun's own server functions, which relay Drive sign-in, squad, Strava, Concept2, Garmin and location-name requests, and hold Garmin access tokens
- **Apple Health (HealthKit) / Health Connect** — if you connect them, as described above
- **Strava API** — if you choose to connect Strava, as described above
- **intervals.icu API** — if you add your intervals.icu key, as described above
- **Concept2 Logbook API** — if you choose to connect your Logbook, as described above
- **Garmin Connect Developer Program (Activity and Training APIs)** — if you choose to connect Garmin, as described above
- **OpenStreetMap (Nominatim)** — general location name of on-water sessions, from a rounded position
- **Open-Meteo** — wind during on-water sessions, from a rounded position and time

## Your choices

- Location and motion permissions can be revoked at any time in your device settings; the app will not record on-water sessions without them.
- Camera access (Coach) is optional and only requested when you use the video recording feature.
- You can disconnect Google Drive, Apple Health or Health Connect, Strava, intervals.icu, the Concept2 Logbook or Garmin at any time from the app's settings, and skip the Logbook upload for any workout. To fully revoke Health access, also remove BoatRun in the Health app (Profile → Apps) or in Health Connect.
- Sharing your training load with a coach is off unless you turn it on, and can be turned off at any time.
- You can delete session data at any time from within the app, or by deleting files from your Google Drive `appDataFolder`.
- You can delete your entire account and its associated data at any time from Metrics → Settings → Your Data → Account.

## Children's privacy

BoatRun is not directed at children and we do not knowingly collect data from children under 13.

## Changes to this policy

We may update this policy as the app evolves. Material changes will be reflected here with an updated date.

## Contact

[support@boatrun.au]
