# 📱 StudentSync

**A campus companion app for college students — built with Java & Android.**

---

## 📋 Table of Contents

- [About](#about)
- [The Problem](#the-problem)
- [Features](#features)
- [Screens](#screens)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Data Model](#data-model)
- [User Flow](#user-flow)
- [Development Timeline](#development-timeline)
- [Project Status](#project-status)
- [Getting Started](#getting-started)
- [Future Plans](#future-plans)

---

## About

**StudentSync** is an Android mobile application designed to help college students stay connected to campus life and academic resources — all in one place.

Right now, finding out about an event, a scholarship, or where the tutoring center is means digging through emails, checking multiple websites, or hoping you saw a flyer. StudentSync fixes that. Open the app, search for something, and find it — whether it's a FAFSA workshop, a coding club meeting, or advising hours.

> 🏫 Built for Mobile App Development | Professor Ogunlana | Spring 2026
> 👩🏾‍💻 Developer: Anaiah Apple | Version 1.0 (Prototype)

---

## The Problem

A lot of community college students — especially first-year and commuter students — miss out on resources simply because they didn't know about them. Events get posted across three different platforms, scholarship deadlines get buried in emails, and campus services feel invisible unless you already know where to look.

StudentSync solves this by centralizing everything into one searchable, filterable, student-friendly app.

---

## Features

### 🔍 Search & Filter
- Search bar on the Home screen to look up events, scholarships, or resources by keyword
- Quick filter tabs: **Events**, **Scholarships**, **Resources**
- Featured events displayed on the Home screen so students see things right away

### 🗺️ Campus Map
- Interactive map powered by **Google Maps Android SDK**
- Pins dropped at each event and resource location on campus
- Tap a pin to see a quick event preview pop-up

### 📄 Event Detail Pages
- Full event info: photo, description, date, time, and location
- **Save / Bookmark** button to add to your personal list
- **Add to Calendar** button — opens your phone's calendar with the event pre-filled

### 👤 User Profile
- Set your interests (Tech, Career, Scholarships, etc.)
- View your saved events in one place
- Scholarship match suggestions based on your interests *(low priority, v1 stretch goal)*

### 🔐 Login & Auth
- Sign up and log in with email and password via **Firebase Authentication**
- Your saved events and preferences are tied to your account

---

## Screens

| Screen | Description |
|---|---|
| **Home** | Search bar, filter tabs, featured events list |
| **Map** | Google Maps view with event pins and tap previews |
| **Event Detail** | Full event info, Save and Add to Calendar buttons |
| **Profile** | User info, interests, saved events, scholarship matches |

All four screens are accessible via a **bottom navigation bar** that stays visible throughout the app.

---

## Tech Stack

| Tool / Service | Purpose |
|---|---|
| **Java** | Primary app language |
| **Android Studio** | IDE for development |
| **Android XML Layouts** | Building screen UIs |
| **Firebase Firestore** | Cloud database for events and user data |
| **Firebase Authentication** | Email/password login and sign-up |
| **Google Maps Android SDK v2** | Interactive campus map with pins |
| **Android CalendarContract** | Built-in intent to add events to phone calendar |
| **MockFlow WireframePro** | UI wireframing |
| **Git / GitHub** | Version control |

---

## Architecture

StudentSync follows a standard **MVC (Model-View-Controller)** pattern:

```
┌─────────────────────────────────────────────┐
│                  StudentSync                │
│                                             │
│  View         →  XML Layouts + Activities   │
│  Controller   →  Java (SearchController,    │
│                         MapController)      │
│  Model        →  Firebase Firestore +       │
│                  local JSON (backup)        │
│                                             │
│  External APIs:                             │
│  [ Google Maps SDK ]  [ Firebase Auth ]     │
│  [ CalendarContract ]                       │
└─────────────────────────────────────────────┘
```

### User Roles

| Actor | Capabilities |
|---|---|
| **Student** | Search events, view map, save events, add to calendar, manage profile, login/register |
| **Admin** | Post and manage events, add scholarships, pin campus locations |

---

## Data Model

Each event is stored as a document in **Firebase Firestore** with the following fields:

| Field | Type | Description |
|---|---|---|
| `eventId` | String | Auto-generated unique ID |
| `title` | String | Name of the event |
| `category` | String | Event, Scholarship, or Resource |
| `description` | String | Full event description |
| `date` | Timestamp | Date and time of the event |
| `location` | String | Building and room number |
| `latitude` | Double | Map pin coordinate |
| `longitude` | Double | Map pin coordinate |
| `imageUrl` | String | Link to event photo |
| `isFeatured` | Boolean | Whether it shows on Home screen |

---

## User Flow

**Primary path:**
```
Open App → Home Screen → Search or Browse → Event Detail → Save or Add to Calendar → Check Profile
```

**Other common paths:**
```
Open App → Map → Tap Pin → Event Detail → Save
Open App → Profile → Login → See Scholarship Matches
Open App → Home → Filter by Resources → Find Tutoring or Advising Info
```

---

## Development Timeline

| Phase | Task | Target |
|---|---|---|
| 1 | Proposal & Requirements Doc | Week 1 |
| 2 | UI Wireframes & Screen Design | Week 2 |
| 3 | Build the Search / Home Screen | Week 3 |
| 4 | Build the Map Screen | Week 4 |
| 5 | Event Detail Page + Profile Page | Week 5 |
| 6 | Testing, Bug Fixes & Final Submit | Week 6 |

---

## Project Status

🟡 **Planning / Design Stage**

- [x] Concept defined
- [x] Core features scoped
- [x] Design document completed (v2)
- [x] UI wireframes drafted
- [ ] Home screen built
- [ ] Map screen built
- [ ] Event detail + profile screens built
- [ ] Firebase integration complete
- [ ] Testing & final submission

---

## Getting Started

> Prerequisites: **Android Studio**, **JDK 11+**, an Android device or emulator (API 26+), and a Firebase project with Firestore and Auth enabled.

```bash
# 1. Clone the repo
git clone https://github.com/YOUR_USERNAME/StudentSync.git

# 2. Open in Android Studio
File → Open → Select the StudentSync folder

# 3. Add your google-services.json
# Download from your Firebase project console and place in /app

# 4. Add your Google Maps API key to AndroidManifest.xml
# <meta-data android:name="com.google.android.geo.API_KEY" android:value="YOUR_KEY"/>

# 5. Run the app
# Select your emulator or connected device and press Run ▶
```

---

## Future Plans

These features are out of scope for v1.0 but planned for future versions:

- 🔔 **Push notifications** for saved events
- 💬 **Social features** — comments, event check-ins
- 🍎 **iOS support** — possibly via React Native
- 🛠️ **Admin dashboard** — full content management for campus staff

---

> 📱 Developed by Anaiah Apple | Mobile App Development | Spring 2026
> This is a course project prototype designed with real-world usability in mind.
