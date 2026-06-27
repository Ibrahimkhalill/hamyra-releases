# hamyra-releases

Public distribution channel for the Hamyra Android app (source: private repo).

- `update-manifest.json` — what the installed app polls on every launch to
  decide whether a new version is available.
- Releases tab — tagged builds with the `app-release.apk` attached.

## Pushing a new version

1. In the source repo, bump `versionCode` / `versionName` in
   `app/build.gradle.kts` and build the release APK.
2. Create a new Release here with tag `v<versionName>`, attach the APK.
3. Edit `update-manifest.json` in this repo's root:
   - bump `versionCode` and `versionName`
   - point `apkUrl` at the new asset URL
   - write user-facing `releaseNotes`
4. Commit + push. All users get the in-app update prompt on their next launch.
