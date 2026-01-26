# software-construction-mobile-app
# Google Maps Analysis
### 1. App Overview
**Problem Solved:** Helps users navigate the physical world efficiently by providing routes, traffic data, and business information, replacing physical maps and phone books.
**Primary Users:** Commuters, travelers, logistics drivers, tourists, and businesses.

### 2. Core Features
1. **Real-time turn-by-turn navigation** (driving, walking, cycling, public transit)
2. **Interactive map with search and place details**
3. **Live traffic conditions and incident reports**
4. **Offline map downloads**
5. **Saved places, lists, and location sharing**
6. **Street View and satellite imagery**

### 3. Thinking Behind the Scenes
1. **User Interface (UI)**: Map rendering, route overlay, voice guidance panel, buttons for start/stop navigation
2. **Business logic**: Routing algorithm (Dijkstra/A*), traffic data fusion, ETA calculation, rerouting logic
3. **Network / APIs**: GPS service, map tile server, traffic data stream, geocoding API, places API
4. **Data storage**: Cached map tiles, route history, user preferences, offline map packages
5. **Street View**: 360° pan/zoom viewer + Image stitching, transition smoothing + Image Streaming API + Massive image database + High bandwidth required; buffers on slow networks. 

### Part C: Change and Maintainability.
**Scenario:** Optimize the app for low-end smartphones.
### 1. Required Changes
* **UI/Rendering:** Replace 3D building rendering with simple 2D tiles to save GPU/RAM.
* **Data Fetching:** Reduce the resolution of map tiles and Street View images to lower data usage.
* **Background Processes:** Limit background location polling to save battery.

### 2. Broken Features
* **Street View:** High imagery might be disabled or severely degraded.
* **Smooth Animations:** Transitions between route steps might become "jumpy" or static.
* **Offline Maps:** Storage limitations on low-end phones might restrict how large an area can be saved.

### 3. Difficulty Reasoning
This is difficult because Google Maps relies heavily on vector graphics and real-time data processing. Stripping these down requires maintaining a separate "Lite" codebase, e.g., Google Maps Go.

### Part D: Software Construction Challenges
1. **Scalability of real-time data**: Handling millions of concurrent users requesting live traffic, routes, and map tiles.
2. **Battery and performance optimization**: Continuous GPS and network usage drain battery; must optimize location polling and background tasks.
3. **Cross-platform and device fragmentation**: Supporting different OS versions, screen sizes, and hardware capabilities across Android and iOS.
4. **Data synchronization and offline support**: Ensuring offline maps stay updated and synced with the user’s saved places and routes.
5. **Security and privacy**: Protecting user location history, securing API keys, and complying with global data regulations (GDPR, etc.).

### Part E: Group Reflection
1. **What surprised your group most about the complexity behind this app?**
We were amazed by how many interconnected systems, including mapping, routing, traffic, search, and third-party integrations, must work together seamlessly in real time.

2. **Why is writing "working code" not enough for software systems at this scale?**
Because the system must be maintainable, scalable, secure, and should perform across diverse environments, code must be clean, well-documented, and collaboratively developed to allow team scaling and long-term evolution.

3. **What did you learn about teamwork from this exercise?**
Clear role division, regular sync-ups, and using GitHub for collaboration made our workflow efficient. Discussing different perspectives helped us understand the app more.


## Group Contributions

| Student Name | Role/Contribution |
| :--- | :--- |
| KIRABO DANIEL NTEZA | **Coordinator:** Managed group schedule and finished the README. |
| KIRABO ESTHER KEBIRUNGI | **App Analyst:** Identified core features and user graphics. |
| KAYONGO ALOYSIOUS | **Systems Thinker:** Analyzed the routing algorithms and API connections. |
|KAKAIRE FORTUNE SHAWN| **Risk Analyst:** Developed the "Low-end optimization" scenario.
|OWINO ESTHER LYN | **Doc Lead:** Created the table and read the submission. |
