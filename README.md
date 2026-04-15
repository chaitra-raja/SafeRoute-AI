# 🛡️ SafeRoute AI — Smart Urban Safety Navigation

> AI-powered micro-solution prototype that recommends the safest commuter route in Bangalore using real-time weather data, simulated crime/lighting/crowd metrics, and a weighted scoring algorithm.

---

## 🎯 Problem Statement

Urban commuters — especially students and night travelers — face unsafe routes due to poor lighting, low crowd presence, and crime-prone areas. Current navigation apps optimize for **time**, not **safety**.

## ⚙️ Solution

SafeRoute AI evaluates multiple candidate routes between two Bangalore locations and recommends the **safest** one in real time.

---

## 🧠 AI Logic — Safety Scoring Formula

```
Safety Score = (Lighting × 0.3) + (Crowd × 0.3) − (Crime × Weight) − Weather Penalty
```

| Factor | Weight | Description |
|--------|--------|-------------|
| Lighting | × 0.3 | Street light quality (1-10) |
| Crowd Density | × 0.3 | Pedestrian foot traffic (1-10) |
| Crime Risk | × 0.4 (Day) / × 0.6 (Night) | Historical incident rate (1-10) |
| Weather Penalty | −1.5 (Rain) / −0.4 (Clouds) | Live from OpenWeather API |

**Higher score = Safer route**

---

## 🚀 Features

| Feature | Status |
|---------|--------|
| Source/Destination selection (Bangalore) | ✅ |
| Day/Night mode toggle | ✅ |
| Live weather API integration (OpenWeather) | ✅ |
| Dynamic safety scoring with formula | ✅ |
| Step-by-step calculation breakdown | ✅ |
| Route comparison bar chart | ✅ |
| Summary recommendation dashboard | ✅ |
| Safe checkpoints (public places) | ✅ |
| "Low safety zone" live alert | ✅ |
| Weather-based smart alerts | ✅ |
| Why safe/risky bullet explanations | ✅ |
| Loading animation | ✅ |
| Accessible (ARIA labels, contrast) | ✅ |
| Mobile-first premium UI | ✅ |

---

## 📊 Simulated Route Data

Each source→destination pair maps to 3 candidate routes with unique safety profiles:

```json
{
  "Majestic→Koramangala": [
    { "route": "MG Road → Hosur Road",   "lighting": 8, "crowd": 7, "crime": 3 },
    { "route": "KR Market Back Lanes",    "lighting": 5, "crowd": 4, "crime": 6 },
    { "route": "Cubbon Park → Ejipura",   "lighting": 6, "crowd": 8, "crime": 4 }
  ]
}
```

6 real Bangalore trip pairs are pre-mapped with fallback defaults.

---

## 🌦️ Weather Integration

- **API:** OpenWeatherMap (free tier)
- **Endpoint:** `api.openweathermap.org/data/2.5/weather?q=Bangalore`
- **Data used:** `weather[0].main` (condition), `main.temp` (temperature)
- **Impact:** Rain applies −1.5 penalty, Clouds −0.4, Clear has no penalty

---

## 🏃 How to Run

1. Open `index.html` in any modern browser, OR
2. Start a local server:
   ```bash
   python -m http.server 8000
   ```
   Then visit `http://localhost:8000`

No dependencies to install. Pure HTML + CSS + JavaScript.

---

## 📱 UI/UX Design

- **Dark/Navy gradient** background with glassmorphism cards
- **Green glow** highlights safest route
- **Red border** flags high-risk routes
- **Bar chart** for instant visual comparison
- **Calculation breakdown** shows the math for transparency
- **Safe checkpoints** suggest nearby public safe stops
- **Loading spinner** during async weather fetch
- **Smooth animations** on card entry

---

## 🏗️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Structure | HTML5 (semantic) |
| Styling | Vanilla CSS (custom properties, glassmorphism) |
| Logic | Vanilla JavaScript (async/await) |
| Icons | Lucide Icons (CDN) |
| Fonts | Google Fonts — Outfit |
| Weather | OpenWeather API |

---

## 📁 File Structure

```
PromptWars-SafeRoute/
├── index.html    # Complete single-file application
└── README.md     # Project documentation
```

---

## 👤 Author

Built as a prototype for the PromptWars Urban Mobility challenge.

---

## 📜 License

MIT — Free to use and modify.
