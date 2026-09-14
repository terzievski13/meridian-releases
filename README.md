# Meridian — releases

Build artifacts for Meridian, a single-user focus timer for macOS. **The source lives in a private repository; this one holds
only the built files**, because a downloaded app and an auto-update need a
public URL and nothing else here needs to be public.

Nothing is developed here. There are no issues, no pull requests, and no code.

## What each release contains

| File | What it is |
| --- | --- |
| `Meridian.dmg` | What a person downloads. The disk image, at a filename that does not change between releases so a download link never goes stale |
| `Meridian.app.tar.gz` | The same app, as the updater fetches it |
| `Meridian.app.tar.gz.sig` | That archive's signature |
| `latest.json` | The update manifest — version, date, and where the archive is |

The app checks `latest.json` when it launches and verifies the signature against
a public key compiled into it. An update that is not signed by the matching
private key is refused.

## Installing

Download `Meridian.dmg` from the latest release and drag Meridian to
Applications. The first launch is blocked by macOS, because this build is not
notarized — press **Done**, *not* "Move to Trash", then open **System Settings →
Privacy & Security** and press **Open Anyway**. Once only; after that it opens
normally and keeps itself up to date.
