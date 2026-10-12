# Elmo Tracker — GFL2: Exilium Pull Tracker

A Windows gacha pull tracker for **Girls’ Frontline 2: Exilium (GFL2 / GF2)**. Import your procurement history, then view banner pity, doll and weapon copy costs, and outfit records.

A fork of [ElmoBeacon](https://github.com/MatchaCabin/ElmoBeacon).

[Download](https://github.com/vitafinn/elmo-tracker-gfl2/releases) · [Report a bug](https://github.com/vitafinn/elmo-tracker-gfl2/issues) · [中文说明](docs/README.zh-CN.md)

![Elmo Tracker showing GFL2 procurement history, banner pity, and pull results](docs/images/overview.png)

## Install

Requires **Windows x64** and the **Windows game client**. Open Access Record inside the game. Capture is built into Elmo Tracker; no Fiddler or separate mitmproxy installation is needed.

1. Download the **windows-x64.zip** from Releases. Do not choose “Source code.”
2. Extract the ZIP to a folder you can write to. Run `ElmoTracker.exe`.

**Updating:** close it, back up `ElmoBeacon.db`, then put the new EXE in the same app folder. Your records and settings stay in place.

If WebView2 is missing, the app offers to download and run Microsoft's installer. It needs an internet connection. [Manual download](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) is only a fallback.

The executable is unsigned. Darkwinter and Haoplay (Global, Asia, Japan, Korea) import paths are included; regional testing is not complete. China-client imports are not supported.

## Import records

1. Open the game and sign in.
2. In Elmo Tracker, select **Import records → My game UID**. Enter the UID from your game profile.
3. Select **Connect to game history**. If setup appears, read the short explanation and select **Continue to Windows**. Check that the Windows prompt names the certificate shown in the app, then select **Yes** to allow capture or **No** to cancel.
4. In the game, open a running banner → **Details → Access Record** side tab. If Access Record is already open, close and reopen it. No pull or purchase is needed.
5. When the app says **History connected**, select **Sync records**. Check the UID and region, then confirm. Wait for **Sync complete**.

Darkwinter users can also choose **Darkwinter webshop sign-in**. Follow the app’s steps and wait for **Webshop UID captured** before opening Access Record. Use the same account in the webshop and game; the app cannot verify that they match.

**Next time:** select **Sync records**. Reconnect only if the connection has expired. Keep using the same UID and import method.

## Certificate and saved data

Capture temporarily uses a local HTTPS proxy and a trusted root certificate. Root trust is a real security permission; read the setup explanation before accepting it. **Remove certificate trust after a successful import** is on by default. You can also remove trust from **Import records → Capture settings**. A valid saved connection can still sync without reinstalling it.

Keep your app folder. Before updating, close the app and back up `ElmoBeacon.db`. Do not share your database, session files, game logs, or `ca.key` (the certificate’s private signing key). The app shows the certificate folder during setup.

[Certificate details and connection troubleshooting](docs/GUIDE.md#capture-privacy-and-troubleshooting)

## Screenshots

Copy costs, luck estimates, and the import steps.

<details>
<summary>View screenshots</summary>

![Copy costs, including preceding losses](docs/images/copy-costs.png)

![Estimated luck compared with the reference chart](docs/images/luck-comparison.png)

![Built-in capture and import](docs/images/import-records.png)

</details>

## Read your stats

- Custom and Reunion banners have separate pity counters that expire. Outfit records are grouped by season.
- Select a result to see copies, preceding losses, and available doll/weapon costs, including V6R1 and V6R6.
- Use **Edit target result** only when a label is wrong. Choose **Unknown** if you do not know.
- Stats use imported history, not your live inventory. Luck values are estimates; missing records can affect them.

## Maintenance and credits

This fork focuses on bug fixes and game compatibility. No new features or regular release schedule are planned. English and Chinese interfaces are included.

Original code and copyright notices are retained under [GPL v3](LICENSE). Release downloads include corresponding source. Chart: 一棵平衡树; English translation: DiggusDBickus. Game names and assets belong to their owners.

[Build instructions](docs/GUIDE.md#develop-and-build) · [Security](SECURITY.md)
