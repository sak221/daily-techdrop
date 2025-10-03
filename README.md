# daily-techdrop

A minimalistic Android App that delivers **5 curated tech news headlines** once a day, at the time the user chooses.
Goal: Make news-consumption feel like a **daily ritual** rather than a constant spam

## Vision
- User picks a **daily drop time** (e.g., 7:00am).
- At that time, the app surfaces the **top 5 tech headlines** in a clean widget on the home/lock screen.
- Tapping a headline opens the full article link.
- Designed to be **lightweight, distraction-free, and predictable**.

  ---

## 📌 Features (MVP scope)
- [ ] Onboarding: user sets preferred drop time.
- [ ] Scheduled background job fetches daily headlines.
- [ ] Home screen widget shows latest 5 tech headlines (collapsed → expanded view).
- [ ] Headlines clickable → open in browser (Chrome Custom Tabs).
- [ ] Settings screen to change time & sources.

---

## ⚙️ Tech Stack Decisions
- **Language**: Kotlin
- **UI**: Jetpack Compose (for app UI)
- **Dependency Injection**: TBD (likely Hilt)
- **Networking**: Retrofit + OkHttp + Moshi
- **Persistence**: DataStore for settings
- **Background jobs**: WorkManager
- **Widget tech**: **Glance**  
  - ✅ Reason 1: Compose-like API → consistent dev experience with Jetpack Compose  
  - ✅ Reason 2: Easier to build modern, reactive widgets compared to legacy RemoteViews

---

## 📰 Candidate News Sources
| Provider        | Type     | Free Tier / Limits | License/Terms | Notes |
|-----------------|----------|-------------------|---------------|-------|
| **NewsAPI.org** | REST API | 100 requests/day  | Requires attribution | Covers tech category directly, easy JSON |
| **The Verge RSS** | RSS feed | Free, unlimited | Public RSS, but must link to Verge | Easy to parse, but less structured |

👉 **Decision:** Start with **The Verge RSS** (safe, unlimited, no API key). Add NewsAPI.org later if quota allows.

---

## 🛠️ Project Setup Status
- [ ] Repo initialized (`main` + `develop` branches).
- [ ] Android Studio project created.
- [ ] Compose screen placeholder: `"TechDrop — Settings"`.
- [ ] Time picker placeholder.
- [ ] Widget scaffold (Glance) — next step.

---

## 📝 Next Steps
1. Finalize simple settings model (`DailyDropSettings` with `timeOfDay`, `enabled`, `sources`).
2. Connect placeholder time picker in Compose.
3. Prepare network client + DTO for chosen news source.
