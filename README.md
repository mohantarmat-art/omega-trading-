# Omega Trading — Android Studio project

This project packages the current Omega Trading HTML as an Android app using Android WebView.

## Build an APK

1. On a computer, install Android Studio (current stable) and the Android SDK Platform 35.
2. Extract this project folder from the ZIP.
3. Open the `OmegaTradingAndroid` folder in Android Studio.
4. Let Gradle sync and install any requested Android SDK components.
5. Choose **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
6. Android Studio will show the APK location, usually `app/build/outputs/apk/debug/app-debug.apk`.
7. Transfer the APK to your Android phone, open it, and allow installation from that source if Android asks.

## Important data and safety notes

- The HTML is bundled at `app/src/main/assets/index.html`; to update the app, replace that file with a newer Omega Trading HTML and rebuild.
- WebView local storage is separate from Chrome/browser local storage. Before moving to the APK, export a journal backup from the existing HTML app. After opening the APK, use the app's import/restore feature if available. Do not delete the old HTML/browser data until you have verified the journal and profile data in the APK.
- The existing two-loss daily cutoff is part of the bundled HTML. This wrapper does not add any mechanism to override it; test the lockout before relying on the APK for live trading decisions.
- TradingView, online chat, and other internet-based features need a network connection. Local journal availability depends on the HTML's own storage implementation.
- This is a source project, not a precompiled APK. The current build environment has Java but no Android SDK/Gradle installation, so an APK could not be compiled or runtime-tested here.

## Optional: build in the cloud from a phone

The ZIP includes a GitHub Actions workflow at `.github/workflows/build-apk.yml`. If you use GitHub:

1. Create a new repository and upload the extracted project contents (including the hidden `.github` folder).
2. Open the repository's **Actions** tab and select **Build Omega Trading APK**.
3. Tap **Run workflow** (or push to the `main` branch to trigger it).
4. When the workflow finishes, open that run and download the `Omega-Trading-debug-APK` artifact. GitHub requires you to be signed in.

This cloud build path still needs a GitHub account and has not been executed from this environment.
