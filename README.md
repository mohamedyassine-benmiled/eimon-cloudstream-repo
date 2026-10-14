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

This version displays the website's list. Timestamps are labels: automatic timestamp resume and progress uploads are future features. Playback extraction is delegated to the separately installed Phisher AniKoto extension.

Android 6+ required. The extension saves an encrypted website session on your device, not your password. Use **Forget login** to disconnect or switch accounts. Login and playback should be tested on your device; this release is not advertised as device-tested.

## Updates

Refresh repositories in Cloudstream to receive new versions. This repository contains binaries and install manifests; the source is maintained separately.
