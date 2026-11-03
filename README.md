# Pixel 9 Pro XL — Native GNSS Speedometer, Heading & Altitude APK

A native Android (`minSdk 29`, `targetSdk 35`) OLED GNSS Speedometer, Heading, and Altitude HUD built specifically for the Pixel 9 Pro XL.

## Key Features
- **Hardware GNSS Direct Access**: Uses `LocationManager.GPS_PROVIDER` at 5Hz (200ms min interval) + `GnssStatus.Callback` for real-time satellite lock counts (`SATS: used/total`).
- **True MSL Altitude on Pixel 9 Pro XL**: Automatically uses Android 14/15 `location.mslAltitudeMeters` (Mean Sea Level geoid-corrected altitude) with fallback to WGS84 ellipsoid altitude.
- **Tap-to-Toggle Units**:
  - **Speed (Large Center Digits)**: Tap the speed card to cycle `MPH` -> `KM/H` -> `KTS` -> `M/S`, or tap `.0` to toggle decimal precision.
  - **Heading (Smaller Digits + Compass Rose)**: Tap the heading card to cycle `DEG + CARD` -> `DEG ONLY` -> `CARDINAL`.
  - **Altitude (Smaller Digits)**: Tap the altitude card to toggle `FEET (FT)` and `METERS (M)`.
- **Pure `#000000` OLED Theme + Always-On Wake Lock**: Uses `FLAG_KEEP_SCREEN_ON`, immersive fullscreen mode, auto-rotate layout (Portrait & Landscape), and 5 selectable OLED accent colors in `MENU`.

---

## Option 1: Compile the `.apk` Automatically in the Cloud (No Android Studio Needed)
This project includes a ready-to-run **GitHub Actions** workflow (`.github/workflows/build-apk.yml`) that compiles the `.apk` automatically on GitHub's servers:

1. Create a free repository on [GitHub](https://github.com/new) and upload the contents of this folder (making sure to include the `.github/workflows/build-apk.yml` file).
2. Click the **Actions** tab in your GitHub repository.
3. Click the **Build Pixel 9 Pro XL GNSS APK** workflow run, scroll down to **Artifacts**, and download **`Pixel9-GNSS-Speedometer-APK.zip`**.
4. Unzip it on your Pixel 9 Pro XL and tap **`app-debug.apk`** to install.

## Option 2: Build Locally in Android Studio
1. Extract this `.zip` archive and open the `Pixel9GnssSpeedometer` folder in **Android Studio**.
2. Wait for Gradle Sync to finish, then select **Build -> Build Bundle(s) / APK(s) -> Build APK(s)**.
3. Copy `app/build/outputs/apk/debug/app-debug.apk` to your Pixel 9 Pro XL and install it.
