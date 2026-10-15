# Eimon Cloudstream Repo

Public binary releases for Eimon's Cloudstream extensions.

## Add to Cloudstream

Open **Settings → Extensions → Add repository** and enter:

```text
https://raw.githubusercontent.com/mohamedyassine-benmiled/eimon-cloudstream-repo/builds/repo.json
```

Repository name: **Eimon Cloudstream Repo**.

## AniKoto Account

Browse **Continue Watching**, **Watching – New Episodes**, **Latest Updated**, **Most Popular**, and **Ongoing**, and search anime within AniKoto Account.

Phisher AniKoto's catalog lists/search are reused where available, with public website catalog/search fallbacks if needed. Public browsing/search works without login. Your personal Continue Watching and Watching – New Episodes lists need the saved account session. Phisher AniKoto is still needed for title details and playback. Version 6 removes the separate Spotlight row.

### Watching – New Episodes (v6)

On Home refresh, this row compares all pages of your website Continue Watching list with the **first three Latest Updated pages** (up to about 90 recent titles). It shows a title only if your saved episode is **at least 80% watched** and a **higher-numbered episode in the same sub/dub version** is available in those recent listings. Matching uses the title URL, not its display name.

No matches or no login means the Home shelf is omitted. Cards label the latest available episode and your saved episode; they open the regular title page, not automatic episode/timestamp resume. Movies, ambiguous/fractional episode numbers, and unknown durations are skipped. This uses website progress; unsynced local progress does not count. Older updates beyond the three recent pages are outside this check.

1. Install **AniKoto Account** from this repository.
2. For playback, also install **AniKoto** from **Phisher Repo**:
   ```text
   https://raw.githubusercontent.com/phisher98/cloudstream-extensions-phisher/refs/heads/builds/repo.json
   ```
3. Restart Cloudstream after installing both extensions.
4. Open **AniKoto Account's settings/gear button → Sign in**.
5. Log in on Anikoto, then tap **Use this session**.
6. Select **AniKoto Account** on Home and refresh.

Browse its rows or search with **AniKoto Account** selected. Results stay under this provider rather than opening directly through Phisher, allowing the account extension to register episodes for optional sync. After updating from an older version, restart the app and refresh Home to load the new rows. In-app navigation and sync still need device verification; adding browsing lists does not establish that the progress bridge is working on every host version.

**Android login popup (v7):** reserves a real browser height to address the reported empty-browser area where only buttons appeared. It also adds Reload and page-loading error messages. If the page still fails, update/enable Android System WebView or Chrome and report the error shown in the popup. This layout change still needs a device retest; cs3d uses the same login/session flow as before.

Timestamps on the list are labels, not automatic seek/resume. Playback extraction is delegated to the separately installed Phisher AniKoto extension.

### Optional progress uploads (v3, experimental)

After signing in, open the extension's **gear → Sync / account options → Enable uploads**. Then reopen an anime through **AniKoto Account** and watch in the app's built-in player. Search through AniKoto Account also works; opening directly in Phisher's provider is not covered.

The extension sends newly saved player position/duration to your Anikoto website history roughly every 20 seconds, with a trailing update after the host stops saving positions. Wait about 10 seconds after stopping before exiting. Check **Sync / account options** for last-upload status. Refresh the website to check the saved episode/time.

Version 4 adds diagnostic counts for matched episodes, extracted playback data, local progress events, and queued uploads. It also prepares a title already loaded through AniKoto Account when uploads are enabled and recognizes delivered playback-link callbacks regardless of the underlying provider's Boolean return value. If uploads do not occur, report the status message and counts from **Sync / account options**. Exact pause/exit event hooks are not implemented by this update.

Uploads are **off by default**. The bridge depends on the local history format in Cloudstream Android/cs3d, and needs device testing. It does not upload old history, change local history, fabricate watched-time/mana rewards, or automatically seek to website timestamps. Only matched anime episodes are supported; ambiguous/special/multi-season episode matches and movies may be skipped. External players/casting may not report positions. Offline pending updates are memory-only and are lost on app exit. Avoid simultaneous playback on multiple devices: local positions can overwrite newer website progress. Disable uploads in the same menu if you do not want website history changed.

Version 2 stores the session using SharedPreferences, available in Cloudstream Android and cs3d Windows, with no Android Keystore dependency. The session cookie is **unencrypted** in app data: do not share preference files or backups. Your password is not stored. Use **Forget login** to disconnect or switch accounts. Android users upgrading from version 1 must sign in again once. Android 6+ or cs3d's compatibility runtime is required; login, restart/persistence, and playback still need device testing.

## Updates

Refresh repositories in Cloudstream to receive new versions. This repository contains binaries and install manifests; the source is maintained separately.
