# GPX Loop Start & Finish Mover

Change where a circular GPX route starts and finishes, without breaking the track.

## Use

Open `index.html` in a browser (or host it on GitHub Pages), then:

1. Upload or drag in a `.gpx` file.
2. Choose a start mode:
   - **On the route**: tap the route, drag the flag, or use the slider to move the start along the loop.
   - **Anywhere + connector**: tap anywhere on the map (or drag the flag). The route walks from your flag to the nearest part of the loop, goes all the way round, then walks back to your flag.
3. Click **Export**, check the track name, edit it if needed, then download or share.

Your route stays in your browser. For an "Anywhere + connector" start, these are sent elsewhere:
- the start point and the loop point it joins, to the OpenStreetMap routing service (OSRM, `router.project-osrm.org`) for a walking path. If that fails, the connector is a straight line and labelled as such.
- the start point and a search radius, to the Overpass API (`overpass-api.de`) for nearby car parks, stations, bus stops and path signposts. If that fails, you are told, and you can still use the start.

## What it does

- **One track out.** Gaps between segments, and between the end and start of the loop, are bridged with straight-line points. The output is a single `<trk>` with a single `<trkseg>`.
- **Connector start.** Start anywhere, not just on the route. The connector follows a walking path (OpenStreetMap data), drawn as dotted purple on the map, and is included in the export. The walking path is requested once per start point and reused for the return.
- **Direction arrows.** Large arrows about every kilometre show the direction of travel.
- **Bridge warning.** If the original route had a gap, the app shows its length and draws the bridge in orange. Check the bridge if it crosses ground you didn't cover.
- **Nearby access.** In connector mode the app lists car parks, stations, bus stops and path signposts near your start. Tap one to start there. If there's nothing close, you get a warning, but you can still use the start.
- **Name before export.** The export screen lets you edit the track name. The name is written into the GPX and used for the filename.
