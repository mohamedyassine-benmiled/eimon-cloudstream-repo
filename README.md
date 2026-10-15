# Eimon Cloudstream Repo

Public binary releases for Eimon's Cloudstream extensions.

## Add to Cloudstream

Open **Settings → Extensions → Add repository** and enter:

```text
https://raw.githubusercontent.com/mohamedyassine-benmiled/eimon-cloudstream-repo/builds/repo.json
```

Repository name: **Eimon Cloudstream Repo**.

## AniKoto Account

Browse your Anikoto website's Continue Watching list, with episode and timestamp labels.

1. Install **AniKoto Account** from this repository.
2. For playback, also install **AniKoto** from **Phisher Repo**:
   ```text
   https://raw.githubusercontent.com/phisher98/cloudstream-extensions-phisher/refs/heads/builds/repo.json
   ```
3. Restart Cloudstream after installing both extensions.
4. Open **AniKoto Account's settings/gear button → Sign in**.
5. Log in on Anikoto, then tap **Use this session**.
6. Select **AniKoto Account** on Home and refresh.

Timestamps on the list are labels, not automatic seek/resume. Playback extraction is delegated to the separately installed Phisher AniKoto extension.

### Optional progress uploads (v3, experimental)

After signing in, open the extension's **gear → Sync / account options → Enable uploads**. Then reopen an anime through **AniKoto Account** and watch in the app's built-in player. Search through AniKoto Account also works; opening directly in Phisher's provider is not covered.

The extension sends newly saved player position/duration to your Anikoto website history roughly every 20 seconds, with a trailing update after the host stops saving positions. Wait about 10 seconds after stopping before exiting. Check **Sync / account options** for last-upload status. Refresh the website to check the saved episode/time.

Uploads are **off by default**. The bridge depends on the local history format in Cloudstream Android/cs3d, and needs device testing. It does not upload old history, change local history, fabricate watched-time/mana rewards, or automatically seek to website timestamps. Only matched anime episodes are supported; ambiguous/special/multi-season episode matches and movies may be skipped. External players/casting may not report positions. Offline pending updates are memory-only and are lost on app exit. Avoid simultaneous playback on multiple devices: local positions can overwrite newer website progress. Disable uploads in the same menu if you do not want website history changed.

Version 2 stores the session using SharedPreferences, available in Cloudstream Android and cs3d Windows, with no Android Keystore dependency. The session cookie is **unencrypted** in app data: do not share preference files or backups. Your password is not stored. Use **Forget login** to disconnect or switch accounts. Android users upgrading from version 1 must sign in again once. Android 6+ or cs3d's compatibility runtime is required; login, restart/persistence, and playback still need device testing.

## Updates

Refresh repositories in Cloudstream to receive new versions. This repository contains binaries and install manifests; the source is maintained separately.
