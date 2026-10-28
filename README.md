# GPX Loop Start & Finish Mover

Change where a circular GPX route starts and finishes, without breaking the track.

## Use

Open `index.html` in a browser (or host it on GitHub Pages), then:

1. Upload or drag in a `.gpx` file.
2. Choose a start mode:
   - **On the route**: tap the route, drag the flag, or use the slider to move the start along the loop.
   - **Anywhere + connector**: tap anywhere on the map (or drag the flag). The route runs from your flag to the nearest part of the loop, goes all the way round, then returns to your flag.
3. Click **Export**, check the track name, edit it if needed, then download or share.

Everything runs locally in your browser. Your route is not uploaded anywhere.

## What it does

- **One track out.** Gaps between segments, and between the end and start of the loop, are bridged with straight-line points. The output is a single `<trk>` with a single `<trkseg>`.
- **Connector start.** Start anywhere, not just on the route. The connector lines are dotted purple on the map and are included in the export.
- **Direction arrows.** Large arrows about every kilometre show the direction of travel.
- **Bridge warning.** If the original route had a gap, the app shows its length and draws the bridge in orange. Check the bridge if it crosses ground you didn't cover.
- **Name before export.** The export screen lets you edit the track name. The name is written into the GPX and used for the filename.
