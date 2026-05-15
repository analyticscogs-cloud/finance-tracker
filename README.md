# Finance Tracker — Android App

A native Android WebView wrapper for the Finance Tracker Google Apps Script webapp.

---

## Project Structure

```
FinanceApp/
├── app/
│   ├── src/main/
│   │   ├── java/com/financetracker/app/
│   │   │   ├── SplashActivity.java   ← Branded splash screen (2s)
│   │   │   └── MainActivity.java    ← WebView host
│   │   ├── res/
│   │   │   ├── layout/
│   │   │   │   ├── activity_splash.xml
│   │   │   │   └── activity_main.xml
│   │   │   ├── drawable/
│   │   │   │   └── splash_gradient.xml
│   │   │   ├── mipmap-*/             ← App icon (all densities)
│   │   │   ├── values/
│   │   │   │   ├── strings.xml
│   │   │   │   ├── colors.xml
│   │   │   │   └── themes.xml
│   │   │   └── xml/
│   │   │       └── network_security_config.xml
│   │   └── AndroidManifest.xml
│   └── build.gradle
├── build.gradle
├── settings.gradle
└── gradle.properties
```

---

## Features

| Feature | Detail |
|---|---|
| Splash screen | Branded gradient + logo, 2 s auto-dismiss |
| WebView | Full JS, DOM storage, cookies (Google auth) |
| Pull-to-refresh | Swipe down to reload |
| Back navigation | Hardware back navigates WebView history |
| Offline handling | Error screen with "Try Again" button |
| Network security | HTTPS-only, no cleartext traffic |
| Orientation | Portrait-locked for stable layout |
| Min SDK | Android 5.0 (API 21) |
| Target SDK | Android 14 (API 34) |

---

## Build Instructions

### Prerequisites
- Android Studio Hedgehog (2023.1) or later  
- JDK 17 (bundled with Android Studio)  
- Android SDK with API 34 platform

### Steps

1. **Open in Android Studio**
   ```
   File → Open → select the `FinanceApp/` folder
   ```

2. **Sync Gradle**  
   Android Studio will prompt — click **Sync Now**.

3. **Run on device / emulator**  
   Press ▶ Run or `Shift+F10`.  
   Make sure the device/emulator has internet access.

4. **Build release APK**
   ```
   Build → Generate Signed Bundle / APK → APK
   ```
   - Create a new keystore (save it safely — you'll need it for updates)
   - Choose `release` build variant
   - APK will be in `app/release/app-release.apk`

---

## Customisation

| What | Where |
|---|---|
| Webapp URL | `MainActivity.java` → `WEBAPP_URL` constant |
| App name | `res/values/strings.xml` → `app_name` |
| Splash tagline | `res/values/strings.xml` → `tagline` |
| Brand colours | `res/values/colors.xml` |
| Splash gradient | `res/drawable/splash_gradient.xml` |
| App icon | Replace `res/mipmap-*/ic_launcher.png` |
| Splash duration | `SplashActivity.java` → `SPLASH_DURATION` (ms) |

---

## Publishing to Google Play

1. Create a **Google Play Developer** account (one-time $25 fee).  
2. Generate a signed **AAB** (Android App Bundle) — preferred over APK.  
3. Fill in store listing: title, description, screenshots, icon (512×512 px).  
4. Set content rating via the questionnaire.  
5. Publish to Internal → Closed → Open testing before production.
