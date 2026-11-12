# BoatRun Privacy Policy

**Last updated:** 12 November 2026

BoatRun is a set of rowing performance apps (the BoatRun app for Row, Cox and Coach, the Viewer and the Analyser). This policy explains what data each app accesses, why, and where it goes.

## Data we collect and why

**Location (GPS)** — BoatRun uses your phone's GPS while recording a session to calculate boat speed, pace, distance and heading. Location data is used only during active recording and is stored in the session file you create.

**Motion & orientation sensors** — BoatRun uses the phone's accelerometer and gyroscope (DeviceMotion) to detect stroke timing, rowing technique metrics (catch quality, drive characteristics, recovery run, etc.) and boat heading. This data never leaves your device except as part of a session file you choose to save or sync.

**Session details you add** — session names, notes, boat type and the race flag are saved with the session file.

**Location name and wind** — for on-water sessions, BoatRun looks up a general location name (for example "Hunter River, Newcastle") and the wind during the session. See *Location names and weather* below.

**Camera and microphone** — Coach can optionally record short videos of a rower's technique during a session. Video is saved locally on the coach's device as a file and is not uploaded automatically to any server.

**Session data (Firebase Realtime Database)** — While a squad session is active, live stroke rate, pace, position and rower name are sent to a Firebase Realtime Database so the Coach and Viewer apps can display them in real time. This data is transient — it reflects live session state and is not retained as a permanent log by us.

**Google Drive (App Data folder)** — If you link Google Drive, completed session files are saved to a hidden app-specific folder in your own Google Drive (`appDataFolder` scope). This folder is not visible in your normal Drive file list and cannot be accessed by other apps. Only you can access this data through your Google account.

**Account (optional)** — You can sign in with Google or Apple. BoatRun stores the account identifier returned by that provider along with your subscription tier, so Pro features unlock on any device you sign in to. BoatRun never creates or holds a password.

**Squad code** — Coach and Viewer use a short code you create or enter to link rowers, coaches, and spectators to the same live session. No account or personal identity is required to use this feature.

## Location names and weather

- **Location name** — the session's start position, rounded to about 100 m, is sent through BoatRun's own server to **OpenStreetMap** (Nominatim), which returns the nearest river, lake or town. No name, account or other session data is sent with it. Results are cached for 30 days so the same spot is not looked up again. Location names © OpenStreetMap contributors, ODbL.
- **Wind** — a position from the session, rounded to about 100 m, and the session's date and time are sent to **Open-Meteo** to get the wind speed and direction for that hour. No other data is sent.
- Both lookups happen only for on-water sessions and only when the phone has a connection. If they fail, the session is saved without them.

## Strava and Concept2 Logbook

- **Strava** — if you choose to connect Strava, BoatRun requests permission to upload activities on your behalf. A session (GPS track, heart rate if recorded, and rowing metrics) is uploaded to your Strava account only when you choose to export it. BoatRun does not read, store or analyse your existing Strava activities or profile beyond what's needed to complete the upload.
- **Concept2 Logbook** (erg sessions, Pro) — if you choose to connect your Logbook, BoatRun asks Concept2 for permission to add workouts on your behalf. When an erg workout finishes, the name screen shows **Upload to C2 Logbook**; it is on by default once you have connected, and you can tap it to skip that workout. An upload contains the workout's date, time zone, time, distance, splits or intervals, stroke rate and count, drag factor, calories, heart rate (if recorded), stroke-by-stroke data, your Logbook weight class and the session name. The upload passes through BoatRun's own server on its way to Concept2. BoatRun uses this access only to add workouts to your Logbook.
- Access tokens for Strava and Concept2 are kept in the app on your device. Disconnecting in the app's settings removes them. Activities and workouts already uploaded stay in your Strava account or Logbook and must be deleted there.

## What we don't do

- We do not sell your data.
- We only pass data to the services listed in this policy, and only for the purposes described here.
- We do not use your data for advertising.
- We do not track you across other apps or websites, and the apps contain no analytics or tracking scripts.
- We do not require an account to record sessions in BoatRun, or to use Viewer or Analyser. An account is only needed to carry a Pro subscription across devices.

## Data storage and retention

Session data is stored locally on your device by default. If you enable Google Drive sync, session files are stored in your own Google Drive account under our control only insofar as our app writes/reads that folder — we do not have separate server-side copies. Live Firebase data used for Coach/Viewer sessions is not retained after the session ends. If you sign in, a single account record (identifier plus subscription tier) is retained in Firebase until you delete your account. Location-name lookups are cached on BoatRun's server for 30 days against the rounded position only, with nothing that identifies you.

## Deleting your account

You can delete your BoatRun account and its data at any time from within the app: **Metrics → Settings → Your Data → Account → Delete My Account**. You will be asked to confirm twice; the action is permanent and cannot be undone.

Account deletion permanently removes:

- Your BoatRun sign-in record (the linked Google or Apple account held by BoatRun)
- Your subscription tier / entitlement record in Firebase
- Your live squad membership entry, so you no longer appear on any coach's screen
- All BoatRun session files stored in your Google Drive app-data folder, if Drive is linked at the time of deletion

Sessions saved locally on your device are not affected and can be deleted separately from the in-app session log. Purchase and billing records held by Apple or Google are retained by those companies under their own policies and for the period required by law; BoatRun cannot delete them. Deleting your account does not cancel an active subscription — cancel that in the App Store or Google Play subscriptions screen.

If you are unable to sign in, email bigwig.91mash@icloud.com from the address linked to your account and deletion will be carried out manually within 30 days.

## Third-party services used

- **Google Drive API** — for optional session backup/sync (your own Drive account)
- **Google Sign-In / Sign in with Apple** — for account sign-in and Drive authentication
- **RevenueCat** — subscription purchase and entitlement management on our behalf
- **Firebase Realtime Database (Google Cloud)** — for live squad coaching data during active sessions, and the account record
- **Cloudflare Workers** — BoatRun's own server functions, which relay Drive sign-in, squad, Strava, Concept2 and location-name requests
- **Strava API** — if you choose to connect Strava, as described above
- **Concept2 Logbook API** — if you choose to connect your Logbook, as described above
- **OpenStreetMap (Nominatim)** — general location name of on-water sessions, from a rounded position
- **Open-Meteo** — wind during on-water sessions, from a rounded position and time

## Your choices

- Location and motion permissions can be revoked at any time in your device settings; the app will not record on-water sessions without them.
- Camera access (Coach) is optional and only requested when you use the video recording feature.
- You can disconnect Google Drive, Strava or the Concept2 Logbook at any time from the app's settings, and skip the Logbook upload for any workout.
- You can delete session data at any time from within the app, or by deleting files from your Google Drive `appDataFolder`.
- You can delete your entire account and its associated data at any time from Metrics → Settings → Your Data → Account.

## Children's privacy

BoatRun is not directed at children and we do not knowingly collect data from children under 13.

## Changes to this policy

We may update this policy as the app evolves. Material changes will be reflected here with an updated date.

## Contact

[bigwig.91mash@icloud.com]
