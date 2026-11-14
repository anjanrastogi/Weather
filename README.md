# Dayweather

A static weather and local discovery app. It runs without API keys and can be hosted on GitHub Pages or Vercel.

## Features

- Search for a city or use the browser's location permission.
- Current conditions, feels-like temperature, humidity, wind, rain, sunrise/sunset, and a live clock in the location's time zone.
- Animated weather symbol and day/night or cloudy/rainy background.
- A 24-hour hourly forecast and an SVG temperature trend chart.
- Current U.S. Air Quality Index (AQI) with particulate readings and plain-language guidance.
- A 30-day planning view. The first 16 days use Open-Meteo forecast data; days 17–30 use historical seasonal averages when available. Those later days are explicitly labeled as a climate outlook, not a forecast.
- Nearby parks, gardens, beaches, viewpoints, museums, attractions, and other mapped places. Suggestions are sorted against the current conditions.

## Data sources and limits

- Weather, geocoding, and air quality: [Open-Meteo](https://open-meteo.com/). Air quality is a model-based estimate, not a monitoring-station reading. U.S. AQI bands are displayed. Air quality data is based on Copernicus CAMS models and can differ from local sensors. Its free forecast API returns up to 16 days. A reliable free daily forecast for 30 days is not generally available, so Dayweather marks the remaining days as a broad historical climate outlook. Seasonal averages cannot predict specific rain or weather events.
- Nearby places: [OpenStreetMap](https://www.openstreetmap.org/) through the public Overpass API. Availability and map coverage can vary. OSM attribution is shown in the app.
- Location access requires HTTPS (or localhost) and explicit browser permission. Searching by place works without location permission.
- This is a static front-end: there are no secrets or API keys to configure. Public free services can impose fair-use limits and may occasionally be unavailable.

## Run locally

You can open `index.html` directly for most features. For a local web server, from this folder run:

```bash
python -m http.server 8000
```

Then open <http://localhost:8000>.

## Publish on GitHub Pages

1. Create a GitHub repository and upload the files in this folder (keep `index.html` at the repository root).
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. Wait for the Pages URL to appear. Use HTTPS for browser location access.

## Deploy on Vercel

1. Push this folder to a GitHub repository.
2. In Vercel, choose **Add New → Project** and import that repository.
3. Framework preset: **Other**. Leave the build command and output directory empty; the project is static.
4. Deploy. No environment variables are required.

## Customization

- `index.html` contains the page structure.
- `styles.css` contains the responsive layout, animations, and themes.
- `app.js` contains API requests, weather rules, and rendering.

## License

The app source is provided for reuse. Weather data is subject to Open-Meteo's terms. Map data is © OpenStreetMap contributors and is available under the Open Database License; retain the displayed attribution when redistributing.



