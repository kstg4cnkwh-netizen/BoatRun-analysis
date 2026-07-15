# BoatRun Privacy Policy

**Last updated:** 9 July 2026

BoatRun is a set of rowing performance apps (Metrics, Coach, Viewer, Analyser). This policy explains what data each app accesses, why, and where it goes.

## Data we collect and why

**Location (GPS)** — Metrics uses your phone's GPS while recording a session to calculate boat speed, pace, and distance. Location data is used only during active recording and is stored in the session file you create.

**Motion & orientation sensors** — Metrics uses the phone's accelerometer and gyroscope (DeviceMotion) to detect stroke timing and rowing technique metrics (catch quality, drive characteristics, etc.). This data never leaves your device except as part of a session file you choose to save or sync.

**Camera and microphone** — Coach can optionally record short videos of a rower's technique during a session. Video is saved locally on the coach's device as a file and is not uploaded automatically to any server.

**Session data (Firebase Realtime Database)** — While a Coach session is active, live stroke rate, pace, and position data is sent to a Firebase Realtime Database so the Coach and Viewer apps can display it in real time. This data is transient — it reflects live session state and is not retained as a permanent log by us.

**Google Drive (App Data folder)** — If you sign in with Google, completed session files are saved to a hidden app-specific folder in your own Google Drive (`appDataFolder` scope). This folder is not visible in your normal Drive file list and cannot be accessed by other apps. Only you can access this data through your Google account.

**Squad code** — Coach and Viewer use a short code you create or enter to link rowers, coaches, and spectators to the same live session. No account or personal identity is required to use this feature.

## What we don't do

- We do not sell or share your data with third parties.
- We do not use your data for advertising.
- We do not track you across other apps or websites.
- We do not require an account to use Metrics, Viewer, or Analyser.

## Data storage and retention

Session data is stored locally on your device by default. If you enable Google Drive sync, session files are stored in your own Google Drive account under our control only insofar as our app writes/reads that folder — we do not have separate server-side copies. Live Firebase data used for Coach/Viewer sessions is not retained after the session ends.

## Third-party services used

- **Google Drive API** — for optional session backup/sync (your own Drive account)
- **Google Sign-In** — for Drive authentication only
- **Firebase Realtime Database (Google Cloud)** — for live squad coaching data during active sessions
- **Strava API** — if you choose to connect Strava, session data (GPS track, heart rate if recorded) is uploaded to your Strava account only when you explicitly trigger an export

## Your choices

- Location and motion permissions can be revoked at any time in your device settings; the app will not record sessions without them.
- Camera access (Coach) is optional and only requested when you use the video recording feature.
- You can disconnect Google Drive or Strava at any time from the app's settings.
- You can delete session data at any time from within the app, or by deleting files from your Google Drive `appDataFolder`.

## Children's privacy

BoatRun is not directed at children and we do not knowingly collect data from children under 13.

## Changes to this policy

We may update this policy as the app evolves. Material changes will be reflected here with an updated date.

## Contact

[Your contact email here]
