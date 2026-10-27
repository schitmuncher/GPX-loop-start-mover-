# GPX Loop Start & Finish Mover

Change where a circular GPX route starts and finishes, without breaking the track.

## Use

Open `index.html` in a browser (or host it on GitHub Pages), then:

1. Upload or drag in a `.gpx` file.
2. Tap the map, drag the flag, or use the slider to move the start point.
3. Export. The file is one continuous track with one closed loop.

Everything runs locally in your browser. Your route is not uploaded anywhere.

## What it fixes

- **Two-part files.** If a GPX has several `<trkseg>` blocks, or the start and end don't meet, the gaps are bridged with straight-line points. The output is a single `<trk>` with a single `<trkseg>`.
- **Seam jumps.** Moving the start point no longer leaves a break where the old start was. The export reports the largest step between points so you can check.
- **Open gaps.** If the original route had a gap, the app shows how far it was and draws the bridge in orange on the map. Check the bridge if it crosses ground you didn't cover.
