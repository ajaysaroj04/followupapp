# FollowUp – Android build

## Build (Windows/Mac/Linux)
1. Install Node.js (18+) and Android Studio (it includes the SDK + JDK).
2. In this folder run:  npm install   then   npx cap sync android
3. npx cap open android   (opens Android Studio; wait for Gradle sync)
4. Build > Generate Signed App Bundle / APK > **Android App Bundle** > create a new keystore
   (BACK UP the keystore + passwords; you need them for every update) > release.
   Output: android/app/release/app-release.aab  <- upload this to Play Console.
   For a test APK: Build > Build APK(s) (debug) and install it on your phone.

## Before publishing
- App id is com.acsinfotech.followup (capacitor.config.ts + android/app/build.gradle). Change BEFORE first upload; it cannot change later.
- Version: android/app/build.gradle -> versionCode (increase every upload), versionName.
- Icon/splash: replace the files in android/app/src/main/res/mipmap-* (or use: npm i -D @capacitor/assets; put icon.png 1024x1024 in /assets; npx capacitor-assets generate --android).
- Play Console needs: privacy policy URL, Data safety form (the app stores data only on the device), screenshots, content rating.
- Edit the web app in www/index.html, then run npx cap sync android and rebuild.
