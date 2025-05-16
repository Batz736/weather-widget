## 🧠 How It Works (Step-by-Step)

This OBS widget uses a browser source to display real-time weather and time information for any city in the world — with no API keys required.

Here’s how it works behind the scenes:

### 1. Time & Date
- The widget uses your selected timezone (via the `timezone` parameter) to display the correct time and date.
- Time updates every second using JavaScript's built-in `Date` object, adjusted to your specified timezone via `Intl.DateTimeFormat`.

### 2. Weather Data
- Weather is pulled from **[wttr.in](https://wttr.in)**, a lightweight weather service that returns weather information as plain text or JSON.
- We make a fetch call to `https://wttr.in/{city}?format=j1`, which gives:
  - Current temperature (°F/°C)
  - "Feels like" temperature
  - Weather condition (e.g., cloudy, sunny)
  - Humidity and other optional data

### 3. URL Parameters Control What’s Displayed
You can customize the widget through the URL by changing parameters:

| Parameter  | Example                | Purpose                                |
|------------|------------------------|----------------------------------------|
| `city`     | `Chicago`              | City name                              |
| `state`    | `IL`                   | State/province abbreviation            |
| `country`  | `US`                   | 2-letter ISO country code              |
| `timezone` | `America/Chicago`      | Timezone using the [TZ database](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) |

✅ Example: index.html?city=Los%20Angeles&state=CA&country=US&timezone=America/Los_Angeles


### 4. Designed for OBS
- The widget is meant to be loaded in OBS as a **Browser Source**.
- It has a transparent background and resizes cleanly to any stream layout.
- Fonts and layout are chosen for legibility even at small sizes.

---

## 💡 Want to Customize More?

You can clone the repo and modify `index.html` directly to:
- Change fonts or colors
- Add or remove data points
- Translate text into another language
- Switch °F to °C or vice versa as the default
