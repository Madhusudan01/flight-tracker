# 3D Flight Tracker — Setup Guide

## Requirements
- Python 3 (already installed on Mac — type `python3 --version` to check)
- Chrome or Firefox

## How to run (takes 10 seconds)

1. Put both files (`server.py` and `index.html`) in the same folder.

2. Open Terminal, navigate to that folder:
   ```
   cd ~/Downloads/flight-tracker
   ```

3. Start the server:
   ```
   python3 server.py
   ```

4. Open your browser and go to:
   ```
   http://localhost:8080
   ```

That's it. The globe and live flights will appear.

## Why this is needed
- CesiumJS requires serving from HTTP (not file://) to load terrain and imagery
- OpenSky Network blocks direct browser requests (CORS) — the Python server fetches data on your behalf

## Controls
- **Click** any aircraft → info panel with callsign, altitude, speed, heading
- **Follow this plane** → camera locks behind aircraft and tracks it in real-time
- **Globe view** → zooms back out to Earth view
- **Refresh now** → manually fetch latest flight data
- Auto-refreshes every 12 seconds

## Color codes
- Blue dot = cruising (8,000m+)
- Green dot = mid-altitude (3–8km)
- Amber dot = low altitude (<3km)
- Gray dot = on ground

## Troubleshooting
- **No flights showing**: OpenSky is rate-limited (100 req/10min anonymous). Wait 30s and hit Refresh.
- **Black globe**: Your Cesium Ion token may need refreshing at ion.cesium.com
- **Server won't start**: Make sure port 8080 isn't in use. Change PORT=8080 in server.py if needed.
# flight-tracker
