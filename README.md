# Self Practice Android Project (Fixed & Production Ready)

This is the fixed and updated Android project for Self Practice (com.selfpractice.app).

## Key Fixes Included:
1. **Android 12+ Compatibility**: Added 'android:exported="true"' to MainActivity in AndroidManifest.xml.
2. **DOM Storage Enabled**: Enabled localStorage and sessionStorage in WebView for quiz persistence.
3. **Hardware Back Button**: Smooth back navigation inside the WebView history.
4. **Target SDK 34**: Aligned with modern Android 14/15 standards.
5. **Instant Cloud Build**: Pre-configured GitHub Actions CI/CD (.github/workflows/build-apk.yml).

## How to Build the Debug APK:

### Option 1: Instant Cloud Build (No Android Studio required)
1. Push this folder to a new GitHub repository.
2. Go to the "Actions" tab on GitHub.
3. The build will run automatically and provide a direct download link for `app-debug.apk` under Artifacts!

### Option 2: Android Studio
1. Open Android Studio -> "Open" -> select this folder.
2. Click **Build -> Build Bundle(s) / APK(s) -> Build APK(s)**.
3. Once built, click **locate** in the popup notification to get `app-debug.apk`.

### Option 3: Terminal CLI
```bash
./gradlew assembleDebug
```
The APK will be generated at: `app/build/outputs/apk/debug/app-debug.apk`

## How to Install APK on Phone:
1. Transfer or download `app-debug.apk` to your Android phone.
2. Tap the APK file. If prompted with "Install unknown apps", toggle "Allow from this source".
3. When Google Play Protect shows "Unrecognized app" or "Blocked by Play Protect", tap **More details** -> **Install anyway**.
4. Tap Open and enjoy!
