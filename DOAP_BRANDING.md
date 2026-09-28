# DOAP Talk Android — v0.1.0

This tree is a branded derivative of Nextcloud Talk for Android.

## Baseline

- Upstream: https://github.com/nextcloud/talk-android
- Pinned commit: cc0f18200893185b58943e06f551c138e51e66c4
- DOAP branch: doap/v0.1.0
- Phase-1 build flavor: `generic`
- Android application ID: `com.doap.talk`
- Product name: **DOAP Talk**
- Server product name: **DOAP Workspace**
- Fixed login target: `https://dmail.doap.com`

## Intentional v0.1.0 limitations

The first APK uses the Generic/UnifiedPush code path and does not configure
DOAP Firebase credentials yet. That lets us verify branding, authentication,
chat and calling without accidentally using Nextcloud's Firebase identity.

The launcher graphic is temporary and intentionally contains no Nextcloud logo.
Replace it with the final DOAP Talk artwork before production release.

## Build

On macOS with Android Studio / Android SDK installed:

```bash
cd "/Users/dave/Projects/doap-talk-android"
./gradlew clean assembleGenericDebug
```

APK output is under:

`app/build/outputs/apk/generic/debug/`

## Upstream updates

```bash
git fetch upstream
git log --oneline --decorate HEAD..upstream/master
```

Do not merge upstream blindly. Rebase/merge into a test branch, build, then
exercise login, chat, incoming/outgoing calls, notifications and background
behavior before promoting it.
