# CRATE Community Bundles

Community-contributed production sound packs for [CRATE](https://controlroomcreative.app).

This repository hosts the manifest and metadata for user-submitted audio bundles — sound effects, ambience recordings, stingers, and other production assets shared by the CRATE community.

## How it works

1. The CRATE app fetches `manifest.json` from this repo
2. Users browse available community bundles inside the app
3. Bundle ZIP files are hosted as GitHub Release assets
4. Downloads are SHA-256 verified before extraction

## Contributing

Want to share your own sound packs with the community?

**Submit via the website:** [controlroomcreative.app/community/submit](https://controlroomcreative.app/community/submit/)

Your submission will be reviewed by a moderator. Once approved, your bundle appears in CRATE for everyone to use.

### What makes a good bundle

- **Original content only** — you must own the rights to everything in the pack
- **Production-ready audio** — WAV, AIFF, MP3, FLAC, OGG, or AAC
- **Clear naming** — descriptive filenames (e.g., `rain-heavy-rooftop.wav`, not `track_03_final_v2.wav`)
- **Reasonable size** — under 500 MB per bundle, under 200 files
- **Useful metadata** — a good name, description, and relevant tags

### What not to submit

- Commercial SFX libraries (Boom, SoundSnap, Splice, etc.)
- Copyrighted music or samples
- Content you don't have rights to distribute
- Empty, corrupt, or mislabelled files

## Bundle format

Each bundle is a ZIP archive containing audio files and an optional `bundle-info.json`:

```json
{
  "name": "Weather SFX Pack",
  "description": "Rain, thunder, wind, and hail recordings from various locations",
  "author": "your-display-name",
  "tags": ["weather", "rain", "thunder", "ambience", "nature"],
  "licence": "community-crate-licence-v1"
}
```

If `bundle-info.json` is not included, metadata is taken from the submission form.

## Licence

All content in this repository is shared under the [Community Crate Licence (CCL)](LICENCE.md):

- Free to use in any production (theatre, film, podcast, video, game, live event)
- Attribution appreciated but not required
- Not for resale as raw files or in competing SFX libraries
- Not sublicensable or redistributable outside of finished productions
- Uploaders retain ownership; they grant a non-exclusive, worldwide, royalty-free licence

## Moderation

This repository is moderated by Control Room Creations. Content that violates our [Terms of Service](https://controlroomcreative.app/terms/) or is flagged for copyright infringement will be removed under our [DMCA Policy](https://controlroomcreative.app/dmca/).

Repeat infringers are subject to a three-strike policy resulting in permanent account termination.

## Links

- [CRATE app](https://controlroomcreative.app)
- [Terms of Service](https://controlroomcreative.app/terms/)
- [DMCA Policy](https://controlroomcreative.app/dmca/)
- [Privacy Policy](https://controlroomcreative.app/privacy/)
