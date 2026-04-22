# TaLeRT-V1

**Desktop job alert bot — automating the least desirable human task.**

**Current status:** 🚧 **Planning phase** — some code written yet. This README is a project blueprint.

---

## Overview

TaLeRT-V1 will be an desktop application that periodically scrapes public job boards for IT apprenticeship roles. When a new, relevant role is found, the application will send a notification to your local desktop.

**Why this project exists:**  
Manual job board checks are repetitive and time-consuming for me and i have to balance work on the portfolio with GCSE's and Mandarin practice. This app will automate these processes so users can focus on building portfolios and preparing for interviews.

**Current progress:**  
- [x] Idea conceived
- [x] Project named (TaLeRT-V1)
- [x] GitHub repository created
- [x] README written (this document)
- [ ] First line of code written
- [ ] Basic scraping prototype
- [ ] Working notification system
- [ ] Release-ready app

---

## Planned Tech Stack

| Component | Planned Technology | Purpose |
|-----------|-------------------|---------|
| Language | Python | Windows 11 |
| HTML parsing | beautifulsoup | Web scraping (no API required) |
| Scheduling | Python Import (not yet specified) | Background job scheduling (2x daily) |
| Notifications | NotificationManager |
| Caching | SQLite | Store seen job IDs to avoid duplicate alerts |

**No external APIs.** Everything will be handled locally within the app using python and SQlite.

---

## How It Will Work (Design) (ignore the current list as its not updated yet to match the new Project environment but it is generally correct in function not theory or practice)

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
Visual Studio Code Latest Release

### Steps (To Be Completed) (Ignore this has not been updated yet)
1. Install Android Studio
2. Clone the repository
3. Open the project
4. Build and run

### Permissions Required (To Be Implemented) (This has not been updated yet ie changing the environment from android to windows but the requirements are pretty much the same but worded differently)
- `INTERNET` — for web scraping (Jsoup)
- `POST_NOTIFICATIONS` (Android 13+) — for alerts

---

## Why Kotlin + Jsoup (Not Pure Kotlin Alone) (Ignore for now)

| Approach | Pros | Cons |
|----------|------|------|
| **Pure Kotlin (no Jsoup)** | No external dependencies | Would need to write a custom HTML parser (error-prone, time-consuming) |
| **Kotlin + Jsoup** | Handles malformed HTML, CSS selectors, small footprint | Adds one lightweight library |

For 5+ parsing functions, Jsoup will significantly reduce code complexity and bugs.

---

## Future Plans

- Add support for Mandarin and custom URL suggestions
- Allow custom search keywords (e.g., "Rust apprentice", "embedded trainee")
- Export job list to CSV for tracking applications

---

## License

MIT License — see [LICENSE](LICENSE) file in the repository.

---

## Current Project Screenshots

### Screenshot 1 22/04/26 ###
<img width="1919" height="1079" alt="Screenshot 2026-04-22 170917" src="https://github.com/user-attachments/assets/4a978a4c-e87a-400b-a35f-6fa5eddf4000" />

*Here you can see Visual Studio Code my prefered code editor on the left and on the right you can see the DataBase (DB) backend what is currently visualised with tkinter but later on ie Pre Release and Full Release V1 it will be hidden to the user and replaced by the Job List and their descriptions plus the scrap parameter filter tab, it will also be modern tkinter instead of this older looking version.*

### Screenshot 1 END ###


## Contact

**Justin Wiltshire (O7NGuy)**  
- Portfolio: [torxen.co.uk](https://torxen.co.uk)  
- GitHub: [github.com/O7NGuy](https://github.com/O7NGuy)

---

## Acknowledgements

Planned as part of my IT portfolio. The repository currently contains only this README and a license file.
