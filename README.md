# GPX Loop Start & Finish Mover

Change where a circular GPX route starts and finishes, without breaking the track.

## Use

Open `index.html` in a browser (or host it on GitHub Pages), then:

1. Upload or drag in a `.gpx` file.
2. Choose a start mode:
   - **On the route**: tap the route, drag the flag, or use the slider to move the start along the loop.
   - **Anywhere + connector**: tap anywhere on the map (or drag the flag). The route walks from your flag to the nearest part of the loop, goes all the way round, then walks back to your flag.
3. Click **Export**, check the track name, edit it if needed, then download or share.

Your route stays in your browser. The only thing sent elsewhere is, for an "Anywhere + connector" start, the coordinates of your start point and the loop point it joins. These go to the OpenStreetMap routing service (OSRM, `router.project-osrm.org`) to get a walking path. If that fails, the connector is drawn as a straight line and labelled as such.

## What it does

- **One track out.** Gaps between segments, and between the end and start of the loop, are bridged with straight-line points. The output is a single `<trk>` with a single `<trkseg>`.
- **Connector start.** Start anywhere, not just on the route. The connector follows a walking path (OpenStreetMap data), drawn as dotted purple on the map, and is included in the export. The walking path is requested once per start point and reused for the return.
- **Direction arrows.** Large arrows about every kilometre show the direction of travel.
- **Bridge warning.** If the original route had a gap, the app shows its length and draws the bridge in orange. Check the bridge if it crosses ground you didn't cover.
- **Name before export.** The export screen lets you edit the track name. The name is written into the GPX and used for the filename.
