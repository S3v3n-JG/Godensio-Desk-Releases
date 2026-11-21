# Godensio Desk

Song mastering, video editing and office work in one desk, running on your own device.

## Download

Get the newest version from **[Releases](https://github.com/S3v3n-JG/Godensio-Desk-Releases/releases/latest)**:

| Device | File |
|---|---|
| Mac with Apple Silicon (M1 and newer) | `Godensio-Desk-macOS-Apple-Silicon.zip` |
| Mac with Intel | `Godensio-Desk-macOS-Intel.zip` |
| Windows | `Godensio-Desk-Windows.zip` |
| Android | `Godensio-Desk-Android.apk` |
| Any computer (runs in Chrome or Edge) | `Godensio-Desk-Web.zip` |

Every desk is free for 7 days. After that you need an access token: email plug.in.your.charger@gmail.com with the device code the app shows you.

## Updates

The app checks for a new version each time it opens. When one is out, an **Update available** button appears at the top. You can also check any time: open the **Library** (books icon) → **Updates** → **Check for updates**, press ⌘K (Ctrl+K) → **Check for updates**, or use Help → Check for updates in the Mac and Windows app.

**Download and install** does the update inside the app:

- **Mac and Windows:** the app downloads the new version, closes, replaces itself and opens again. On a Mac there's no Terminal step after an in-app update.
- **Android:** the app downloads the new version and opens Android's installer; tap **Install**. The first time, Android asks you to allow Godensio Desk to install apps.
- **Web version:** download the new zip and unzip it over the old folder.

Your projects, Library and settings stay as they are.

## For the publisher

`feed.json` tells the apps the newest version, where to download it and which access tokens were cancelled. Make it in the Token Generator (Updates tab) and replace the file here.

To release a new version:
1. Raise the version number and build the five files.
2. Create a GitHub Release with the tag `v` + the version (for example `v1.2.0`) and attach the five files with these exact names: `Godensio-Desk-macOS-Apple-Silicon.zip`, `Godensio-Desk-macOS-Intel.zip`, `Godensio-Desk-Windows.zip`, `Godensio-Desk-Android.apk`, `Godensio-Desk-Web.zip`.
3. Update `feed.json` with the new version. The apps pick it up the next time they open.

The apps look for `feed.json` in **Godensio-Desk-Releases** first and in this repository as a backup, so this repository can be made private once a public **Godensio-Desk-Releases** repository holds `feed.json` and the Releases.

### Token Generator and GitHub

In the Token Generator, open **Updates → GitHub connection** and paste a fine-grained GitHub key (Contents: Read and write, only for the repos below). Then:

- **Cancel token**, **Pause**, **Resume** and **Move to a new device** publish the cancelled list to `feed.json` straight away.
- **Publish to GitHub** sends a new version's `feed.json` in one step (create the Release with the five files first).
- The issued-token list is kept in a **private** repo as `tokens.enc.json`, encrypted with the generator passphrase, so every copy of the generator shows the same list. The generator refuses to put it in a public repo.

The GitHub key is stored inside the generator's locked vault. It is never built into the apps.

