# Captions from Speechify TTS speech marks

Synthesizes audio with [`POST /v1/audio/speech`](https://docs.speechify.ai/tts) and converts the word-level `speech_marks` it returns into a valid WebVTT file. The browser then renders the captions automatically via an `<audio>` + `<track>` pair.

## What you get

- `output/sample.mp3` — synthesized audio (already committed, 120 KB, real API output)
- `output/sample.vtt` — matching WebVTT cues, one per word
- `output/sample.json` — the raw `speech_marks` array, kept for reference

Plus two demo pages:

- `demo/karaoke.html` — working audio player with word-by-word highlight, driven by the `cuechange` event on the `TextTrack`
- `demo/mapping.html` — side-by-side visualisation of the `speech_marks` JSON against the resulting VTT cues

## Run it yourself

```bash
cp .env.example .env  # then paste your SPEECHIFY_API_KEY
npm install
npm start             # rewrites output/sample.mp3, .vtt, .json
```

## See the demo pages

```bash
npm run demo          # serves demo/ on http://localhost:8765
```

Open `http://localhost:8765/karaoke.html` and press play.

## Where the code came from

This is the TypeScript native (no-SDK) recipe from the [Speechify Cookbook](https://github.com/SpeechifyInc/speechify-api-cookbook/tree/main/recipes/audio/typescript/native/speech-marks). The cookbook is the canonical home for the recipe; this folder is the matching demo that produces the audio + captions + visualisations the blog post references.

## Prerequisites

- Node 20 or newer
- A `SPEECHIFY_API_KEY` from [console.speechify.ai/api-keys](https://console.speechify.ai/api-keys)
