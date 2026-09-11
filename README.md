# WebView wrapper app

An Android app that opens a single website in a WebView, with its own
style (theme, icon, offline screen, progress bar, back navigation).

## 1. Set your site

Open `app/src/main/java/com/example/webapp/MainActivity.java` and edit:

    private static final String START_URL = "https://perchance.org/CHANGE_ME";

Put the URL the app should open. Optionally change the app name in
`app/src/main/res/values/strings.xml` (app_name) and colors in `colors.xml`.

## 2. Put it on GitHub

Create an empty repository on github.com, then in this folder:

    git init
    git add .
    git commit -m "WebView app"
    git branch -M main
    git remote add origin https://github.com/USERNAME/REPO.git
    git push -u origin main

## 3. Let it build in the cloud

Pushing to `main` triggers `.github/workflows/build.yml`, which builds the
APK on GitHub's servers (nothing to install locally).

On GitHub: **Actions** tab -> the latest run -> download the **app-debug**
artifact. Unzip it to get `app-debug.apk`, copy to your phone and install
(enable "Install from unknown sources"). You can also re-run any time from
the Actions tab with "Run workflow".

## Notes

- Debug APKs are signed with the Android debug key, so they install fine
  for personal use. For a Play Store release you would add your own signing
  keystore via GitHub Secrets and build `assembleRelease`.
- `minSdk 26` (Android 8.0+), `targetSdk 34`.
