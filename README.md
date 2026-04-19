# TaLeRT-V1

**Android job alert bot — automating the least desirable human task.**

**Current status:** 🚧 **Planning phase** — no code written yet. Android Studio not installed. This README is a project blueprint.

---

## Overview

TaLeRT-V1 will be an Android application that periodically scrapes public job boards for IT apprenticeship roles. When a new, relevant role is found, the app will send a push notification to your phone.

**Why this project exists:**  
Manual job board checks are repetitive and time-consuming. This app will automate that process so users can focus on building portfolios and preparing for interviews.

**Current progress:**  
- [x] Idea conceived
- [x] Project named (TaLeRT-V1)
- [x] GitHub repository created
- [x] README written (this document)
- [ ] Android Studio installed
- [ ] First line of code written
- [ ] Basic scraping prototype
- [ ] Working notification system
- [ ] Release-ready app

---

## Planned Tech Stack

| Component | Planned Technology | Purpose |
|-----------|-------------------|---------|
| Language | Kotlin | Modern Android development |
| HTML parsing | Jsoup | Web scraping (no API required) |
| Scheduling | WorkManager | Background job scheduling (2x daily) |
| Notifications | NotificationManager | Push alerts to your phone |
| Caching | SharedPreferences / SQLite | Store seen job IDs to avoid duplicate alerts |

**No external APIs.** Everything will be handled locally within the app using Kotlin and Jsoup.

---

## How It Will Work (Design)

1. **Schedule** — `WorkManager` will trigger the job check at user-defined intervals.
2. **Fetch** — Jsoup will connect to search results URLs (e.g., Reed.co.uk, GOV.UK) and download HTML.
3. **Parse** — Jsoup will select relevant HTML elements containing job titles, locations, and links.
4. **Compare** — New job IDs will be checked against a local cache of previously seen jobs.
5. **Notify** — If a job is new, `NotificationManager` will send an alert to your phone.

**Why Jsoup?**  
Jsoup is the standard Java/Kotlin library for scraping. It handles malformed HTML, supports CSS selectors, and is lightweight.

---

## Legal & Ethical Notice (Will Be Implemented)

- **Public data only:** The app will scrape only publicly accessible data (no login required).
- **Tolerated use:** Scraping is neither explicitly permitted nor prohibited by most job boards. The app will operate under fair use / personal-use exceptions — limited to 2 requests per day per site to mimic human behaviour and avoid server load.
- **No commercial use:** This project is for educational and personal portfolio purposes only.
- **Compliance:** Users will be responsible for checking individual website terms of service. The app will not bypass any technical barriers (e.g., CAPTCHA, authentication).

**If a website explicitly blocks scraping in its robots.txt or terms of service, users should respect that.**

---

## Planned Features

- [ ] Basic HTML scraping with Jsoup (Kotlin)
- [ ] Scheduled background checks (WorkManager)
- [ ] Push notifications for new jobs
- [ ] Local caching (prevents duplicate alerts)
- [ ] Configurable search parameters (location, keywords)
- [ ] Support for multiple job boards
- [ ] In-app settings UI

---

## Setup & Build Instructions (When Ready)

### Prerequisites
- Android Studio (latest version) — not yet installed
- Android device or emulator (API level 24+)

### Steps (To Be Completed)
1. Install Android Studio
2. Clone the repository
3. Open the project
4. Build and run

### Permissions Required (To Be Implemented)
- `INTERNET` — for web scraping (Jsoup)
- `POST_NOTIFICATIONS` (Android 13+) — for alerts

---

## Why Kotlin + Jsoup (Not Pure Kotlin Alone)

| Approach | Pros | Cons |
|----------|------|------|
| **Pure Kotlin (no Jsoup)** | No external dependencies | Would need to write a custom HTML parser (error-prone, time-consuming) |
| **Kotlin + Jsoup** | Handles malformed HTML, CSS selectors, small footprint | Adds one lightweight library |

For 5+ parsing functions, Jsoup will significantly reduce code complexity and bugs.

---

## Future Plans

- Add support for Indeed, CWJobs, and GOV.UK
- Allow custom search keywords (e.g., "Rust apprentice", "embedded trainee")
- Export job list to CSV for tracking applications
- Publish to Google Play Store (if feasible)

---

## License

MIT License — see [LICENSE](LICENSE) file in the repository.

---

## Contact

**Justin Wiltshire (O7NGuy)**  
- Portfolio: [torxen.co.uk](https://torxen.co.uk)  
- GitHub: [github.com/O7NGuy](https://github.com/O7NGuy)

---

## Acknowledgements

Planned as part of my IT portfolio. The repository currently contains only this README and a license file. Code development will begin once Android Studio is installed.
