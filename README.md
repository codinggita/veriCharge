<div align="center">
  
  # ⚡ VeriCharge

  **Next-Generation EV Infrastructure & Smart Queue Management Platform**

</div>

---

## 📌 Overview

**VeriCharge** is a high-performance platform engineered to eliminate range anxiety and streamline the electric vehicle charging experience. The application tackles the critical problem of EV charger availability by utilizing real-time geographic data to connect drivers with the most optimal, time-efficient charging stations.

## 🚀 The Problem We Solve

EV drivers frequently experience **"range anxiety"**—the fear of running out of power before reaching a station. This is compounded by arriving at a station only to find the chargers broken, incompatible, or occupied with a long waiting queue. VeriCharge solves this fragmented experience through three core pillars:

1. **Intelligent Location Discovery**: Instantly scans your current geographic coordinates to pinpoint the nearest operational, high-powered EV charging stations around you.
2. **Predictive Availability Tracking**: Eliminates the frustration of arriving at a full station. VeriCharge provides live telemetry to show you exactly *which* chargers are currently free, their power output (kW), and predicts the exact wait time in minutes for occupied stalls.
3. **Turn-by-Turn Navigation & Reach Time**: Dynamically calculates your real-time travel ETA to any station and seamlessly launches turn-by-turn routing directly within the dashboard, keeping the map camera intelligently rotated in your direction of travel.

## 📡 Third-Party API Integrations

To power the live data ecosystem, VeriCharge seamlessly orchestrates several powerful third-party APIs:

- **[OpenChargeMap API](https://openchargemap.org/)**: The global public registry of electric vehicle charging locations. VeriCharge queries this API in real-time based on your GPS coordinates to fetch nearby stations, hardware capabilities, max power output (kW), and connector compatibility. *(Note: Live availability telemetry is currently simulated on the frontend based on the raw OpenChargeMap POI data).*
- **[OSRM (Open Source Routing Machine)](http://project-osrm.org/)**: Powers the turn-by-turn navigation engine. When you start a route, VeriCharge queries the OSRM backend to calculate the fastest road network polyline and provides live driving instructions (e.g., distance, turn modifiers).
- **[Nominatim (OpenStreetMap)](https://nominatim.org/)**: The geocoding engine driving the search bar. It allows users to search for any city, street, or landmark and instantly converts that human-readable text into exact GPS coordinates to discover charging networks in remote areas.

## 🛠️ Technology Stack & Libraries

The frontend is built with modern, high-performance web technologies:

- **[React](https://react.dev/) (`react`, `react-dom`)**: The core UI library used to build the interactive, component-based dashboard.
- **[Vite](https://vitejs.dev/)**: Next-generation frontend build tool providing an ultra-fast development server and optimized production bundles.
- **[Tailwind CSS](https://tailwindcss.com/)**: Utility-first CSS framework powering the premium, responsive dark-mode aesthetic and complex layout designs.
- **[React Router](https://reactrouter.com/) (`react-router-dom`)**: Handles seamless, client-side routing between the Live Map, History, Reliability, and Support pages without reloading the app.
- **[MapLibre GL JS](https://maplibre.org/) (`maplibre-gl`)**: An open-source, WebGL-based mapping engine used to render the highly interactive, hardware-accelerated 3D live navigation map.
- **[React Map GL](https://visgl.github.io/react-map-gl/) (`react-map-gl`)**: Provides React components and hooks for MapLibre, allowing us to declaratively render the map, user location tracking arrow, and charging station markers.
- **[Leaflet](https://leafletjs.com/) (`leaflet`, `react-leaflet`)**: Open-source mapping libraries retained for legacy 2D map rendering or lightweight fallback views.

## 📍 Location Access & GPS Tracking

VeriCharge relies on the browser's native **Geolocation API** (`navigator.geolocation.watchPosition`) to provide a seamless dynamic map experience without requiring dedicated native mobile apps.

- **Real-Time GPS Tracking**: The app requests location permissions upon loading the Live Map. Once granted, it actively listens for coordinate updates to render a moving 3D navigation arrow and locally recalculate ETAs to nearby stations.
- **Privacy-First & Non-Blocking**: If a user denies location access (or it is disabled), the UI gracefully adapts. The map will load without crashing, displaying a *"Location Denied"* status banner, and completely unblocks the user to manually search for charging stations using the integrated search engine.
- **Dynamic Directional Heading**: Utilizing coordinate deltas (`lastLat`/`lastLng` vs `newLat`/`newLng`), VeriCharge mathematically calculates the user's geographic bearing using spherical trigonometry (`Math.atan2`). This allows the platform to intelligently rotate the 3D map camera ahead of the driver when "Auto-Follow" navigation mode is active.

## 🎨 Design & Prototype

The platform is designed with a premium, state-of-the-art dark mode aesthetic tailored for the modern driver. You can explore the interactive high-fidelity prototype directly in Figma to see the complete user flow and design system.

👉 **[Explore the Interactive Figma Prototype](https://www.figma.com/proto/pZUu5qXerpjH2kAt1CpV6u/Untitled?page-id=0%3A1&node-id=30-3438&p=f&viewport=-287%2C-1647%2C0.47&t=5bYD9XioPioRtTtf-1&scaling=min-zoom&content-scaling=fixed&starting-point-node-id=30%3A4347)**

---

<div align="center">
  <sub>Built for the next generation of mobility.</sub>
</div>