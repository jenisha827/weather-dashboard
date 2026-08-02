# SkyGauge — Weather Testing & Monitoring Dashboard

A glassmorphic weather dashboard that fetches live conditions and a 5-day forecast for any city, charts temperature and humidity trends, and runs an automated **weather safety test** (heat risk, cold risk, rain probability, wind safety, and an air comfort score).

Built with vanilla HTML5, CSS3, and ES6 JavaScript — no frameworks, no build step. Created as a portfolio project.

![SkyGauge dashboard screenshot](assets/icons/screenshot-placeholder.png)
*Replace this with an actual screenshot of the running app before publishing.*

---

## Features

- **City search** — look up current weather for any city worldwide.
- **Current conditions** — temperature, feels-like, humidity, wind speed, pressure, visibility, weather icon and description, sunrise/sunset.
- **5-day forecast** — daily forecast cards derived from the 3-hour forecast data.
- **Trend charts** — temperature and humidity trend lines (Chart.js) over the upcoming forecast window.
- **Weather testing panel** — automated evaluation of:
  - Heat risk
  - Cold risk
  - Rain probability
  - Wind safety
  - Air comfort score (0–100)
  - Overall result: Excellent / Good / Moderate / Poor
- **Color-coded status badges** for every risk category.
- **Loading spinner** during API calls.
- **Error handling** for invalid city names, missing/invalid API keys, and network failures.
- **Dark/light mode toggle**, persisted with `localStorage`.
- **Recently searched cities**, persisted with `localStorage`, one click to re-search.
- **Fully responsive** — works on mobile, tablet, and desktop.
- **Smooth animations & hover effects** throughout.

---

## Technologies used

| Tech | Purpose |
|---|---|
| HTML5 | Semantic page structure |
| CSS3 | Glassmorphism UI, responsive layout, theming via CSS variables |
| Vanilla JavaScript (ES6) | App logic — no frameworks |
| [OpenWeatherMap API](https://openweathermap.org/api) | Current weather + 5-day/3-hour forecast data |
| [Chart.js](https://www.chartjs.org/) | Temperature & humidity trend charts |
| `localStorage` | Theme preference, API key, recent city history |

---

## Getting an OpenWeatherMap API key

1. Go to [openweathermap.org](https://openweathermap.org/) and create a free account.
2. Once logged in, open **My API keys** from your account menu (or go directly to [openweathermap.org/api_keys](https://home.openweathermap.org/api_keys)).
3. Copy the default key generated for you (or click **Generate** to create a new one).
4. New keys can take up to a couple of hours to activate — if you get a 401 error right after signing up, wait and try again.
5. The free tier covers the **Current Weather Data** and **5 Day / 3 Hour Forecast** endpoints used by this app.

You do **not** need to edit any source file to add your key — the app asks for it in the browser and stores it locally (see below).

---

## How to run locally

This is a static site — no build tools or package manager required.

1. **Clone or download** this repository:
   ```bash
   git clone https://github.com/<your-username>/weather-dashboard.git
   cd weather-dashboard
   ```

2. **Open `index.html`** in a browser. Either:
   - Double-click `index.html`, or
   - Serve it locally (recommended, avoids any browser file-origin quirks):
     ```bash
     # Python 3
     python -m http.server 5500
     # then visit http://localhost:5500
     ```
     or with the VS Code **Live Server** extension.

3. **Add your API key**: expand the "OpenWeatherMap API key" panel under the search bar, paste your key, and click **Save**. It's stored only in your browser's `localStorage` — never sent anywhere except directly to OpenWeatherMap.

4. **Search a city** and explore the dashboard.

---

## Folder structure

```
weather-dashboard/
│── index.html
│── style.css
│── script.js
│── README.md
│── assets/
│   └── icons/
```

---

## Future improvements

- Geolocation support ("use my current location") via the Browser Geolocation API.
- Unit toggle (°C / °F, m/s / mph).
- Hourly forecast view in addition to the 5-day cards.
- Air Quality Index integration using OpenWeatherMap's Air Pollution API.
- Weather alerts / severe weather warnings panel.
- Offline caching of the last successful search via a Service Worker.
- Automated tests for the weather-test scoring functions (`evaluateHeatRisk`, `evaluateAirComfortScore`, etc.).
- Deploy to GitHub Pages with a live demo link in this README.

---

## License

This project is open source and available for personal and educational use.
