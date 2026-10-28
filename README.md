# Fredoors — spoken word bank

Pronunciation audio for the [Fredoors](https://fredoors-c3d39.web.app) English
vocabulary app. Nothing here is source code; the app itself lives elsewhere.

## What is in a release

One zip per deck — about 15 recordings, roughly 175 KB — plus a
`manifest.json` listing every pack with its size and SHA-256. The app reads
the manifest once, then fetches only the deck a learner opens and keeps it on
the device. A deck whose pack has not arrived is read aloud by the phone's own
voice instead, so a missing pack is never a broken lesson.

Current release: `audio-v1`.

## Why a release and not a web host

The app's backend is on Firebase's free plan, where Hosting serves 360 MB a
day for the whole project. The bank is 150 MB, so a few hundred learners would
exhaust a day's allowance before lunch. GitHub does not meter release
downloads.

## How it is made

Generated speech, one voice, from the word list shipped inside the app. The
46 words an engine reliably mispronounces — `lead` the metal, `minute`
meaning tiny, `bass` the voice — are generated from the IPA the word list
records for them rather than from their spelling.
