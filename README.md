```markdown
# 🇲🇾 MY Transit Hub — Klang Valley Public Transport Dashboard

A **production‑ready, single‑file HTML dashboard** for Malaysia's Klang Valley public transport system, featuring:

- 🗺️ **Live train and bus positions** via the official GTFS Realtime API (KTMB & Prasarana)
- 🧭 **Journey planner** with BFS routing across 50+ rail stations
- 💰 **Fare estimator** based on straight‑line distance (integrated Rapid KL table planned)
- 🛍️ **Mall & surau finder** — find the nearest malls with prayer‑room details
- 🚌 **Alternative transport** suggestions for every station
- 🌙 Dark glassmorphism UI, fully responsive, no backend required

All data and logic are **self‑contained** in a single HTML file.  
No API keys, no servers, no database — just open the file in a browser.

---

## ✨ Features

### 📋 Info & APIs Tab
- Overview of MRT, LRT, Monorail, KTM Komuter, BRT, and Rapid Bus.
- List of free transit APIs used (GTFS Realtime, Nominatim, Leaflet).

### 💰 Fare Calculator
- Dropdown origin/destination from 50+ stations.
- Computes straight‑line distance with Haversine formula.
- Applies realistic base fare + per‑km rate, capped at RM 6.40 (daily integrated cap).
- Warning about estimates vs. actual path‑based fares.

### 🗺️ Live Map
- **Dark tile layer** (CARTO) centred on Kuala Lumpur.
- Station markers colour‑coded by line.
- **Live KTMB trains** (orange dots) and **Prasarana buses** (blue dots) updated every 30 s from `data.gov.my`.
- Toggle layers, choose bus category (KL, Penang, Kuantan, MRT Feeder).
- Click‑to‑place **origin/destination** markers with straight‑line distance.
- Location search via Nominatim.

### 🧭 Journey Planner
- Builds an adjacency graph from the hardcoded station dataset (including interchanges like KL Sentral, Masjid Jamek).
- **Breadth‑First Search** to find a route between any two stations.
- Displays station sequence, lines, and approximate total distance.

### 🛍️ Mall & Surau Finder (Upgraded)
- A database of **30+ major Klang Valley malls** with exact coordinates.
- For each selected station, shows the **5 nearest malls** (sorted by distance).
- Each mall card includes:
  - Distance from the station.
  - **Surau (prayer room) availability** with location details (e.g., floor, nearby landmark).
- Quick‑reference table of traditional station‑to‑mall direct mappings.

### 🚌 Alternative Transport
- Per‑station list of backup options: Rail Bridging Bus, Rapid DRT van, regular buses, Go KL free bus, KTM Komuter, and e‑hailing.

---

## 🚀 How to Use

1. **Download** the `index.html` file (or clone this repository).
2. **Open it** in any modern web browser (Chrome, Firefox, Safari, Edge).
3. That’s it. The dashboard loads immediately.

No installation, no build tools, no server.

> **Note:** An internet connection is required for:
> - Loading Leaflet and font libraries from CDN.
> - Fetching live GTFS Realtime train/bus positions.
> - Nominatim location search.
>
> All other features (static station data, malls, fare calculator, journey planner) work **completely offline**.

---

## 🛠️ Technology Stack

| Layer           | Technology                                      |
|-----------------|-------------------------------------------------|
| **Frontend**    | HTML5, CSS3, Vanilla JavaScript (ES6+)          |
| **Map**         | [Leaflet](https://leafletjs.com/) + CartoDB dark tiles |
| **Fonts**       | Inter & Poppins (Google Fonts)                  |
| **GTFS Decoder**| [gtfs-realtime-bindings](https://github.com/google/gtfs-realtime-bindings) (protobuf) |
| **Live Data**   | [data.gov.my](https://data.gov.my) GTFS Realtime API |
| **Search**      | [Nominatim](https://nominatim.org) (OpenStreetMap) |

All dependencies are loaded via CDN — the entire application is a single, self‑contained HTML file.

---

## 📡 Data Sources & Credits

- **Station coordinates & graph**: Manually curated from official Rapid KL / KTMB station lists and OpenStreetMap.
- **GTFS Realtime feeds**:  
  - [KTMB vehicle positions](https://api.data.gov.my/gtfs-realtime/vehicle-position/ktmb)  
  - [Prasarana bus positions](https://api.data.gov.my/gtfs-realtime/vehicle-position/prasarana) (various categories)  
  Provided by Malaysia’s open data portal `data.gov.my`.
- **Mall & surau information**: Based on public data from [Carisurau.com](https://carisurau.com) (by Farhan Helmy) and manually verified locations.
- **Alternative transport data**: Compiled from Rapid KL announcements and personal knowledge.

---

## 📸 Screenshots

*(Add screenshots of each tab here — info, fare, live map, journey planner, mall finder, alternative transport.)*

---

## 🧪 Testing Locally

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/my-transit-hub.git
   cd my-transit-hub
```

2. Open index.html in your browser.

For live GTFS data to work, you must be online. If you see no live markers, check your browser’s console for CORS or network issues.

---

🚧 Roadmap / Future Improvements

· Integrate GTFS Static schedules for exact route paths and stop times.
· Add real arrival predictions using GTFS Realtime trip updates.
· Replace straight‑line fare with Rapid KL’s integrated fare table from the static GTFS feed.
· Add MRT Putrajaya Line and more recent station expansions.
· Convert to a Progressive Web App (PWA) for full offline capability with service worker.
· Fetch mall data dynamically if the malaysia-mall-api becomes active.
· Add dark/light theme toggle.

---

🤝 Contributing

Pull requests are welcome!
If you find a bug or want to suggest a feature, please open an issue.

Before contributing, please note that the station graph, mall list, and surau details are maintained manually — any updates should be verified against official sources.

---

📄 License

This project is open source and available under the MIT License.

---

💬 Acknowledgements

· Farhan Helmy for the inspiration via Carisurau.com and the malaysia-mall-api proof‑of‑concept.
· Malaysia’s open data initiative (data.gov.my) for providing free GTFS Realtime and static feeds.
· The Leaflet and OpenStreetMap communities for the mapping infrastructure.
· Rapid KL & KTMB for the actual transport services that make all this useful.

---

Built with ❤️ for the Klang Valley commuter.

```
```