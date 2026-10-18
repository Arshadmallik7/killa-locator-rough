# Killa Locator v2.1: get the APK (free, no Android Studio)

GitHub builds the APK for you on its free servers. You do this once; later updates are the same steps.

## 1. Put the project on GitHub
1. Make a free account at github.com and press **New repository**. Name it `killa-locator`. Choose **Private** (your parcel data stays yours).
2. On the new repository page press **uploading an existing file**.
3. Unzip this project on your PC, open the folder, select everything inside it (`android`, `www`, `package.json`, `package-lock.json`, `capacitor.config.json`, `build-apk.yml`, `.gitignore`) and drag it into the page. Press **Commit changes**.
4. The hidden `.github` folder often does not upload. So add the build file by hand: **Add file > Create new file**, type this name exactly:
   `.github/workflows/build-apk.yml`
   then open `build-apk.yml` from this project in Notepad, copy all of it, paste it in, and press **Commit changes**.

## 2. Build
1. Open the **Actions** tab. If asked, press the green button to enable workflows.
2. Choose **Build Killa Locator APK** on the left, press **Run workflow**, then the green **Run workflow** button.
3. Wait about 5 to 10 minutes until the run shows a green tick.
4. Open the run, scroll to **Artifacts**, download **killa-locator-apk**. Unzip it: inside is `app-debug.apk`.

## 3. Install on the phone
**First time with this version only:** the old APK was signed with a different key, so Android will refuse to install over it. Before uninstalling it, open the app and use Saved points > Download CSV if you want to keep your saved points (offline maps will need downloading again). Then uninstall the old Killa Locator. From now on, every new APK installs over the previous one and keeps your saved points and offline maps.

1. Copy `app-debug.apk` to the phone (WhatsApp to yourself, USB, or Drive).
2. Tap it. If Android asks, allow **Install unknown apps** for the app you opened it from.
3. Open **Killa Locator**. It asks for Location straight away: choose **While using the app** and keep **Precise** on. Also make sure Location (GPS) is switched on in the phone's quick settings.

## 4. Before going to the field (on Wi-Fi)
Open the sheet at the bottom, tap **Offline maps**, and press **Download** beside each village. Leave the app open until the bar finishes. The satellite picture for that village then works with no signal.

## If something fails
- Build turns red: open the failed step in the run and send me the red text.
- Install says "app not installed": uninstall any older copy first, then install again.

## Updating later (more villages, changes)
Replace the changed files in the GitHub repository (for example `www/data.js`), then run the workflow again (step 2). The new APK installs over the old one.
