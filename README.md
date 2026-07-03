# 🎨 Dropper

Change a video's background color right in your browser. No installs, no uploads, no accounts — Dropper is a single HTML file. Open it, drop a video in, click the old color, pick a new one, export. Everything runs locally on your machine.

Sibling of [Clipper](#) and [Plopper](#).

## What it does

- Works with **MP4s that have a flat background** and **transparent WebMs**
- **Click the background in the live preview** to eyedrop the old color — no hex hunting
- Pick the new color and watch the video recolor **live while it plays**
- **Tolerance** and **edge softness** sliders for clean edges around your subject
- Export downloads the recolored video (MP4 where the browser supports it, WebM otherwise)

## How it works

The preview and recolor run on a WebGL chroma-key shader, so it stays real-time even at 1080p. Transparent WebMs skip keying entirely — Dropper composites them over the new color using their actual alpha channel, so edges come out pixel-perfect.

Export uses `canvas.captureStream()` + `MediaRecorder`, which records in real time: a 6-second loop is instant, a 25-minute video takes 25 minutes with the tab open. For very long files, ffmpeg is faster — Dropper shines for loops, quick experiments, and dialing in the exact color before batch work.

## Usage

1. Download `dropper.html`
2. Double-click it — it opens in your browser
3. Drop a video in and go

**Recommended browser:** Chrome or Edge (WebGL + MediaRecorder + transparent WebM playback).

**Privacy:** nothing leaves your machine. There's no server — you can go offline after the page loads and everything still works.

## Why a single HTML file?

Because a tool you can email to a friend, keep in a folder, and open in five years without a build step is underrated. No `npm install`, no rotting dependencies. One file, one job.

## License

MIT — use it, fork it, break it, ship it.

---

*Made with an unreasonable fondness for flat wonky cats.* 🐈‍⬛
