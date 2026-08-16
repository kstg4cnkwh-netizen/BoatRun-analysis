# BoatRun Privacy Policy

**Last updated:** 17 August 2026

BoatRun is a set of rowing performance apps (Metrics, Coach, Viewer, Analyser). This policy explains what data each app accesses, why, and where it goes.

## Data we collect and why

**Location (GPS)** - Metrics uses your phone's GPS while recording a session to calculate boat speed, pace, and distance. Location data is used only during active recording and is stored in the session file you create.

**Motion & orientation sensors** - Metrics uses the phone's accelerometer and gyroscope (DeviceMotion) to detect stroke timing and rowing technique metrics (catch quality, drive characteristics, etc.). This data never leaves your device except as part of a session file you choose to save or sync.

**Camera and microphone** - Coach can optionally record short videos of a rower's technique during a session. Video is saved locally on the coach's device as a file and is not uploaded automatically to any server unless the coach chooses to save files to a cloud drive.

**Username** - You set your own display name in the app. This name is not set or changed by a coach, and is the only identifying label attached to your live and uploaded session data.

**Live session data (Firebase Realtime Database)** - While connected to a Coach session, live stroke rate, pace, and position data is sent to a Firebase Realtime Database so the Coach and Viewer apps can display it in real time. This live broadcast is transient and is not retained after the session ends. All Firebase traffic is encrypted in transit (TLS) and encrypted at rest by Google's infrastructure.

**Sent-to-coach session files** - If you are connected to a coach in Coach mode, your full session file is automatically uploaded to the squad's cloud storage when the session ends, along with your username only. This storage can optionally be password protected by the coach, and is only accessible to squad members at the "coach" role level. Files remain there until the coach prunes them (records older than 21 days are removed automatically) or you request earlier deletion.

**Google Drive (App Data folder)** - If you sign in with Google, completed session files are also saved to a hidden app-specific folder in your own Google Drive (`appDataFolder` scope). This folder is not visible in your normal Drive file list and cannot be accessed by other apps. Only you can access this data through your Google account.

**Squad code** - Coach and Viewer use a 7-digit random code and optional password that the coach creates to link rowers, coaches, and spectators to the same live session. No account or personal identity is required to use this feature.

## What we don't do

- We do not sell or share your data with third parties.
- We do not use your data for advertising.
- We do not track you across other apps or websites.
- We do not require an account to use Metrics, Viewer, or Analyser.

## Data storage and retention

Session data is stored locally on your device by default. If you enable Google Drive sync, session files are stored in your own Google Drive account under our control only insofar as our app writes/reads that folder - we do not have separate server-side copies. Live Firebase broadcast data used for Coach/Viewer sessions is not retained after the session ends. Sent-to-coach session files persist in squad cloud storage until pruned or deleted, as described above.

## Third-party services used

- **Google Drive API** - for optional session backup/sync (your own Drive account)
- **Google Sign-In** - for Drive authentication only
- **Firebase Realtime Database (Google Cloud)** - for live squad coaching data and sent-to-coach session files, encrypted in transit and at rest
- **Strava API** - if you choose to connect Strava, session data (GPS track, heart rate if recorded) is uploaded to your Strava account only when you explicitly link your account

## Your choices

- Location and motion permissions can be revoked at any time in your device settings; the app will not record sessions without them.
- Camera access (Coach) is optional and only requested when you use the video recording feature.
- You can disconnect Google Drive or Strava at any time from the app's settings.
- You can delete session data at any time from within the app, or by deleting files from your Google Drive `appDataFolder`.

## Children's privacy

BoatRun is not designed or marketed for children to use unsupervised. Where BoatRun is used by junior rowers through a school or club program, we rely on the school, club, or a parent/guardian to have obtained any consent required by applicable law before a minor uses the app, and to supervise the minor's access to squad codes and shared data accordingly.

For junior/minor users:
- No account or personal profile is required to use Metrics, Viewer, or Analyser - a squad code alone identifies a rower's device within a session, not the individual.
- The rower sets their own display name; we recommend schools instruct junior rowers to use first name or initials only, not full names.
- We do not use any user's data, including a minor's, for advertising, marketing, or profiling.
- Schools or parents/guardians can request deletion of a junior rower's stored session data at any time by contacting their coach or using the in-app deletion controls described above.

## Changes to this policy

We may update this policy as the app evolves. Material changes will be reflected here with an updated date.

## Contact

[bigwig.91mash@icloud.com]
