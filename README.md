# quran-athkar-data

Downloadable content for the QuranApp iOS app. The app fetches these assets on demand; nothing here is application code.

## Releases

| Release | Contents |
|---|---|
| `manifests-<version>` | Rolling pointer, always marked **Latest**. Holds `quran_images_manifest.json` and `zikr_athkar_manifest.json`. The app reads these from `releases/latest/download/`. |
| `quran-images-v<version>` | Per-Juz Quran page image packs (604 pages, 15 lines per page). |
| `v<version>` | Athkar text and audio packs. |

## Rules

- Only the manifests release is marked Latest. Content releases are created with `--latest=false`, or the app's manifest refresh breaks for every user.
- Every pack entry in a manifest carries a byte `size` and a `sha256`. The app verifies both after download.
- Pack URLs in the manifests are absolute and pinned to a content tag, so manifests and content can version independently.
