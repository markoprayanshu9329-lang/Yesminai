# YESMIN AI (MVP v0.1) — UNTESTED, not yet compiled

## Build
**Workflow B (recommended):** push this folder to GitHub, run the "Build APK" action, download the APK artifact, sideload it.
**Workflow A (Termux):** `pkg install openjdk-17 gradle`, install Android SDK (platform 34, build-tools 34.0.0),
create `local.properties` with `sdk.dir=...`, set an aarch64 aapt2 in gradle.properties, then `gradle assembleDebug`.
APK: `app/build/outputs/apk/debug/app-debug.apk`. Install: `adb install -r <apk>`.
Note: `gradle assembleDebug` uses your installed Gradle (needs 8.7+). Run `gradle wrapper` to add a wrapper.

## Backend (required for AI answers)
Deploy `backend/worker.js` (Cloudflare Worker), set secrets GEMINI_API_KEY and APP_TOKEN.
In the app: Settings → paste the https URL + token → Test connection. Never put the Gemini key in the app.

## Permissions
INTERNET (chat), RECORD_AUDIO (asked at first mic tap). Nothing else.

## Done / Pending
Done: home UI + orb, chat, Gemini via backend (retry/timeouts), 5 personas, voice in/out, app launcher allowlist,
YouTube search, local calculator, settings. Pending: Room history, light theme, coding assistant, notes, reminders,
translation, study mode, AccessibilityService, Hilt.
