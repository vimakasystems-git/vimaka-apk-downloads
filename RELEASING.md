# Publishing a verified APK

1. Build the Android app in its **source repository**.
2. Test on representative Android devices and verify the package ID, permissions, navigation, and links.
3. Sign a release build using the project's dedicated release key, stored securely outside this public repository.
4. Verify the signature with Android SDK's `apksigner verify --verbose app-release.apk`.
5. Compute SHA-256 checksums (e.g. `sha256sum app-release.apk > SHA256SUMS.txt` on Linux).
6. Create a **public GitHub Release** in this repository using an app-specific tag such as `tvillingarnas-maleri-v1.0.0`.
7. Upload the signed APK and the checksum file as release assets. Confirm that a logged-out browser can download the APK.
8. Configure the company's website Worker variable `APK_RELEASE_URL` to the verified release asset URL. Confirm that `/api/android-release` reports availability and the download button works on mobile.
9. Preserve older releases for rollback and update the release notes when publishing fixes.

A GitHub Actions **debug build artifact** is not a production-ready signed APK and cannot substitute for a public GitHub Release. Do not distribute debug keys or credentials.

Suggested naming:
```text
Release tag: tvillingarnas-maleri-v1.0.0
Release asset: tvillingarnas-maleri-v1.0.0.apk
Checksum file: SHA256SUMS.txt
```
