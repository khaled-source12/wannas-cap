# Wannas — How to Build for App Stores

## What's inside this zip
- `android/` → Full Android project (open in Android Studio)
- `ios/` → Full iOS project (open in Xcode)
- `src/` → App source code
- `dist-cap/` → Built web files (already synced into android/ and ios/)

---

## Every time you get updates from Replit
Run these 2 commands inside the `wannas/` folder:

```bash
npm run build:cap
npx cap sync
```

That's it — your Android and iOS projects are now up to date.

---

## Build for Google Play (Android APK)

### Requirements
- Install **Android Studio**: https://developer.android.com/studio
- Install **Java JDK 17+**: https://adoptium.net

### Steps
1. Open Android Studio
2. Click **Open** → select the `android/` folder inside this zip
3. Wait for Gradle to sync (first time takes a few minutes)
4. Go to **Build → Generate Signed Bundle / APK**
5. Choose **Android App Bundle (.aab)** → click Next
6. Create a keystore (first time) or use your existing one
7. Click **Finish** → your `.aab` file is ready to upload to Google Play Console

---

## Build for Apple App Store (iOS)

### Requirements
- A **Mac** (required by Apple — no way around this)
- **Xcode** installed from the Mac App Store
- **Apple Developer Account** ($99/year): https://developer.apple.com

### Steps
1. Open Terminal on your Mac, go to this folder
2. Run: `sudo gem install cocoapods` (first time only)
3. Run: `npx cap open ios` — this opens Xcode automatically
4. In Xcode, select your Team under **Signing & Capabilities**
5. Set the Bundle Identifier to `com.wannas.app`
6. Go to **Product → Archive**
7. Click **Distribute App → App Store Connect → Upload**

---

## App Store accounts you need

| Store | Link | Cost |
|---|---|---|
| Google Play Console | https://play.google.com/console | $25 one-time |
| Apple Developer | https://developer.apple.com | $99/year |

---

## Updating the app in the future

1. Make changes in Replit (as usual)
2. Download the new source zip from Replit
3. Replace the `src/` folder with the new one
4. Run `npm run build:cap && npx cap sync`
5. Rebuild in Android Studio / Xcode and resubmit
