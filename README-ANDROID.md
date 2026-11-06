# NINJA AI Android — Experimental 0.1

This is an Android Studio **source project**, not a signed APK.

## Included
- Login and account registration screens.
- Backend URL field.
- Device registration after successful authentication.
- Basic `/v1/me` connection check.
- Dark cyan NINJA AI visual style.

## Backend compatibility
This prototype expects the NINJA AI v0.3 API:
- `POST /v1/auth/login`
- `POST /v1/auth/register`
- `POST /v1/devices/register`
- `GET /v1/me`

The request bodies use `email` and `password` for authentication, and `device_name` plus `platform` for device registration. If your server's exact v0.3 schema differs, the Android client must be adjusted to match it.

## Build
1. Open this folder in Android Studio.
2. Let Gradle sync.
3. Build > Build Bundle(s) / APK(s) > Build APK(s).
4. Use a server URL reachable from the phone. Prefer HTTPS.

## Important limitations
- No project browser, editor, AI chat, or push/pull sync UI yet.
- No Google Sign-In integration.
- Tokens are held in memory only and are lost when the app closes.
- `usesCleartextTraffic` is enabled for local testing. For deployment, use HTTPS and disable cleartext traffic.
- This is an early prototype, not production-ready. Do not expose an un-hardened test backend to the public internet.

## Build an APK from your phone using GitHub Actions
1. Create a new GitHub repository.
2. Upload the **contents** of this project folder (including the hidden `.github` folder).
3. Open the repository's **Actions** tab.
4. Select **Build NINJA AI Android APK**, then **Run workflow** if it has not started automatically.
5. Open the completed workflow run and download the `NINJA-AI-Android-debug` artifact.
6. Extract the artifact ZIP on your phone and install `app-debug.apk`.

The workflow builds a debug APK. It is for testing, not a signed Play Store release.
