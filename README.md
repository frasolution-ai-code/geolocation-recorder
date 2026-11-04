# How it works

1. **Start recording**  
   - Asks for location permission.  
   - Records a point every second (`watchPosition` + a 1s interval).  
   - Requests a **screen wake lock** so the display stays on (supported in most modern browsers when the page is visible).  
   - Button turns **red** and shows:  
     *“Recording your location. This is sensitive data please think before sharing this data.”*  
   - Shows a live count of recorded points.

2. **Stop recording** (press the red button again)  
   - Stops geolocation and releases the wake lock.  
   - Shows a **read-only** textarea with the full array as pretty-printed JSON, plus a **Copy data** button.

3. **JSON shape** (one array of objects), e.g.:

```json
[
  {
    "latitude": 52.37,
    "longitude": 4.89,
    "accuracy": 12.5,
    "altitude": null,
    "altitudeAccuracy": null,
    "heading": null,
    "speed": null,
    "timestamp": 1729790000000,
    "recordedAt": "2026-10-24T17:47:00.000Z"
  }
]
```

Open the file in a browser (preferably over HTTPS or localhost — geolocation and wake lock usually need a secure context). Allow location when prompted.

