# ChatApp — fixed Android project

This version fixes the build configuration from the original project.

## Important

- Java/JVM target is **17** for both Java and Kotlin.
- AndroidX is enabled.
- The GitHub Actions workflow does **not** try to unzip a missing project ZIP.
- `google-services.json` is optional for compilation. If you put your real Firebase file in `app/google-services.json`, the Google Services Gradle plugin is enabled automatically.
- The APK is uploaded by GitHub Actions as the `ChatApp-debug-apk` artifact.

## Firebase

For real Firebase Authentication/Firestore/FCM operation:

1. Create a Firebase project.
2. Add Android package `com.example.chatapp`.
3. Download the real `google-services.json`.
4. Put it at `app/google-services.json`.
5. Commit it only if that is appropriate for your Firebase project; do not put private credentials or secrets in source control.
6. Enable the Firebase services you use.

## GitHub Actions

The workflow is:

`.github/workflows/android.yml`

It builds directly from the repository. There is intentionally no `unzip ChatAppFirebaseConnected.zip` step.
