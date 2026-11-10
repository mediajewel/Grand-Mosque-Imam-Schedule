# Haram Imam widget

Open this folder in Android Studio (Koala or newer), let Gradle sync, run on a device/emulator,
then long-press the home screen -> Widgets -> "Haram Imam".

- Prayer name/time: calculated offline for Makkah (Umm al-Qura), shown in your phone's local time.
- Imam: scraped from #haram-imam on theislamicinformation.com, only shown if the page's
  "next prayer" matches the calculated one and the data is < 6 h old. Otherwise "Imam not available".
- Refresh: every 15 min, once just after each prayer begins, and when you tap the widget.

If the imam always says "not available", the site fills that field with JavaScript. Fix: find the
JSON request in Chrome DevTools -> Network -> Fetch/XHR and point ImamScraper.fetch() at it.

## Getting an APK without Android Studio
Push this folder to a new GitHub repo. The workflow in .github/workflows/build.yml builds a debug APK
automatically (about 5 min). Open the repo's Actions tab -> latest run -> download "haram-imam-apk".
