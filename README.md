<div align="center">

<img src="app/src/main/res/drawable/logo.jpeg" alt="NammaMistri Logo" width="120" height="120" style="border-radius: 24px;" />

# NammaMistri

### *Your Trusted Local Labour Marketplace*

**Connecting skilled daily-wage workers with hirers — instantly, transparently, and locally.**

[![Android](https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)](https://android.com)
[![Kotlin](https://img.shields.io/badge/Language-Kotlin-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white)](https://kotlinlang.org)
[![Jetpack Compose](https://img.shields.io/badge/UI-Jetpack%20Compose-4285F4?style=for-the-badge&logo=jetpackcompose&logoColor=white)](https://developer.android.com/jetpack/compose)
[![Firebase](https://img.shields.io/badge/Backend-Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com)
[![Min SDK](https://img.shields.io/badge/Min%20SDK-24-blue?style=for-the-badge)](https://apilevels.com)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

</div>

---

## 📖 About

**NammaMistri** is a dual-role Android application that bridges the gap between **skilled daily-wage workers** (carpenters, electricians, plumbers, painters, and more) and **hirers** (homeowners, contractors, and businesses) in local communities across Karnataka.

Workers can list themselves with their skills, daily rate, and availability. Hirers can browse, filter, and directly contact workers or send hire requests — all in real time. Built entirely in **Kotlin + Jetpack Compose** with **Firebase** as the backend, NammaMistri delivers a smooth, native experience with no intermediary commissions.

> *"Namma" (ನಮ್ಮ) means "Our" in Kannada — this is your community marketplace.*

---

## ✨ Features

### 👷 Worker Side
- Create and manage a **professional worker profile** with name, skill, location, daily charge, phone, and WhatsApp number
- Add **multiple skills** with individual daily rates
- Toggle **real-time availability** (Available / Busy / Offline)
- View and respond to **incoming hire requests** from hirers
- **In-app chat** with hirers
- View **saved/favourited** profiles

### 🏗️ Hirer Side
- Browse a **live directory of available workers** with filter by skill and location
- View detailed **worker profiles** with availability badge and contact info
- Send **hire requests** directly to workers
- Track **request status** (Pending / Accepted / Declined)
- **In-app chat** with workers
- Save favourite workers for quick access

### 🔐 Auth & Onboarding
- **Role selection** on first launch — choose Worker or Hirer
- **Email & Password** authentication via Firebase Auth
- Persistent login — stays signed in across sessions

### 💬 Real-time Chat
- One-to-one messaging between workers and hirers
- **Chat list screen** showing all active conversations
- Messages stored securely in Firestore

### 🎨 UI / UX
- Premium **luxury light theme** — bright, clean, and professional
- **Glassmorphism cards** with soft shadows and rounded corners
- **InitialAvatar** — auto-generated coloured avatar from user's name (no broken images)
- Fully **scroll-aware layouts** — submit button always stays above the keyboard
- Smooth **animated transitions** between screens
- Material 3 design system throughout

---

## 🏗️ Tech Stack

| Layer | Technology |
|---|---|
| Language | Kotlin |
| UI Framework | Jetpack Compose + Material 3 |
| Architecture | Single-Activity + Composable screens |
| Authentication | Firebase Auth (Email/Password) |
| Database | Firebase Firestore |
| File Storage | Firebase Storage |
| Image Loading | Coil 2.6 (`AsyncImage`) |
| Icons | Material Icons Extended |
| Build System | Gradle (Kotlin DSL) |
| Min Android | API 24 (Android 7.0 Nougat) |
| Target Android | API 36 |

---

## 📁 Project Structure

```
app/src/main/
├── java/com/karthik/nammakelsa/
│   │
│   ├── 🔑  Auth & Entry
│   │   ├── RoleSelectionActivity.kt   # Launch screen — pick Worker or Hirer
│   │   └── MainActivity.kt            # Login / Register screen
│   │
│   ├── 🏠  Home & Navigation
│   │   ├── HomeActivity.kt            # Root activity with bottom nav
│   │   ├── MainScreen.kt              # Nav host — routes to role-specific tabs
│   │   └── BottomNav.kt               # Bottom navigation bar definitions
│   │
│   ├── 👷  Worker Screens
│   │   ├── WorkerHomeScreen.kt        # Worker dashboard & stats
│   │   ├── WorkerProfileScreen.kt     # Worker's own profile view
│   │   ├── WorkerRequestsScreen.kt    # Incoming hire requests
│   │   └── WorkerListScreen.kt        # (Hirer-facing) browsable worker directory
│   │
│   ├── 🏗️  Hirer Screens
│   │   ├── HirerHomeScreen.kt         # Browse & filter workers
│   │   ├── HirerProfileScreen.kt      # Hirer's own profile view
│   │   ├── HirerRequestsScreen.kt     # Sent hire requests & status
│   │   └── HirerDetailActivity.kt     # Hirer detail viewed by worker
│   │
│   ├── 📋  Shared Screens
│   │   ├── WorkerDetailActivity.kt    # Full worker profile (viewed by hirer)
│   │   ├── EditProfileScreen.kt       # Edit profile (role-aware)
│   │   ├── ProfileActivity.kt         # Profile activity shell
│   │   ├── AddSkillActivity.kt        # Add / manage skills
│   │   ├── SavedWorkersScreen.kt      # Saved / favourite workers
│   │   └── ErrorStateScreen.kt        # Generic error + retry UI
│   │
│   ├── 💬  Chat
│   │   ├── ChatActivity.kt            # Chat activity shell
│   │   ├── ChatListScreen.kt          # All conversations list
│   │   └── ChatScreen.kt              # One-to-one messaging UI
│   │
│   ├── 🎨  UI Components
│   │   ├── GlassComponents.kt         # GlassCard, GlassButton, screenBgBrush
│   │   └── InitialAvatar.kt           # Auto-coloured initial avatar
│   │
│   ├── 📦  Data Models
│   │   ├── Worker.kt                  # Worker data model (Firestore mapping)
│   │   ├── Request.kt                 # Hire request model
│   │   ├── Message.kt                 # Chat message model
│   │   ├── ChatUser.kt                # Chat participant model
│   │   ├── Review.kt                  # Review/rating model
│   │   └── Favorite.kt                # Saved worker model
│   │
│   └── 🎨  Theme
│       ├── Color.kt                   # Full luxury colour palette
│       ├── Theme.kt                   # Light/dark theme config
│       └── Type.kt                    # Typography scale
│
└── res/
    ├── drawable/
    │   └── logo.jpeg                  # App logo
    ├── values/
    │   ├── strings.xml
    │   ├── colors.xml
    │   └── themes.xml
    └── AndroidManifest.xml
```

---

## 🚀 Getting Started

### Prerequisites
- Android Studio **Hedgehog (2023.1.1)** or later
- JDK 17+
- An active **Firebase project** (see setup below)
- Android device or emulator running **API 24+**

### 1. Clone the Repository

```bash
git clone https://github.com/saniyatalikoti/namm_mistri_saniyatalikoti.git
cd namm_mistri_saniyatalikoti
```

### 2. Firebase Setup

1. Go to the [Firebase Console](https://console.firebase.google.com/) and create a new project (or use an existing one).
2. Add an **Android app** with package name `com.karthik.nammakelsa`.
3. Download the `google-services.json` file.
4. Place it in the `app/` directory:
   ```
   app/google-services.json
   ```
5. In the Firebase Console, enable the following services:
   - **Authentication** → Email/Password sign-in method
   - **Firestore Database** → Start in test mode (then apply rules below)
   - **Storage** → For profile photo uploads

### 3. Firestore Security Rules (Recommended)

```js
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {

    // Workers collection — anyone authenticated can read; only owner can write
    match /workers/{workerId} {
      allow read: if request.auth != null;
      allow write: if request.auth != null && request.auth.uid == resource.data.userId;
      allow create: if request.auth != null;
    }

    // Users collection — owner read/write only
    match /users/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }

    // Requests — authenticated users can read/write their own
    match /requests/{requestId} {
      allow read, write: if request.auth != null;
    }

    // Messages — authenticated users only
    match /messages/{messageId} {
      allow read, write: if request.auth != null;
    }
  }
}
```

### 4. Build & Run

Open the project in Android Studio, let Gradle sync complete, then click **Run ▶** or use:

```bash
./gradlew assembleDebug
```

---

## 📦 Dependencies

```kotlin
// Firebase BOM — consistent versioning across all Firebase libraries
implementation(platform("com.google.firebase:firebase-bom:33.5.1"))
implementation("com.google.firebase:firebase-auth-ktx")
implementation("com.google.firebase:firebase-firestore-ktx")
implementation("com.google.firebase:firebase-storage-ktx")

// Image loading
implementation("io.coil-kt:coil-compose:2.6.0")

// Material Icons (full icon set)
implementation("androidx.compose.material:material-icons-extended")

// Jetpack Compose BOM
implementation(platform(libs.androidx.compose.bom))
implementation(libs.androidx.activity.compose)
implementation(libs.androidx.compose.material3)
implementation(libs.androidx.compose.ui)
implementation(libs.androidx.compose.ui.graphics)
implementation(libs.androidx.compose.ui.tooling.preview)

// Core
implementation(libs.androidx.core.ktx)
implementation(libs.androidx.lifecycle.runtime.ktx)
```

---

## 🔄 App Flow

```
App Launch
    │
    ▼
RoleSelectionActivity
    │
    ├──► [New User]  MainActivity (Register with Email/Password)
    │
    └──► [Existing User] MainActivity (Sign In)
              │
              ▼
         HomeActivity (Bottom Navigation)
              │
    ┌─────────┴──────────┐
    │                    │
    ▼                    ▼
 WORKER ROLE          HIRER ROLE
 ────────────         ───────────
 Home (Dashboard)     Home (Browse Workers)
 Requests (Incoming)  Requests (Sent + Status)
 Saved                Saved
 Chat List            Chat List
 Profile              Profile
```

---

## 🗂️ Firestore Data Model

### `workers` collection
| Field | Type | Description |
|---|---|---|
| `userId` | String | Firebase Auth UID |
| `name` | String | Worker's full name |
| `skill` | String | Primary skill |
| `skillsList` | List | All skills with individual rates |
| `location` | String | City / area |
| `chargePerDay` | String | Daily rate in ₹ |
| `phoneNumber` | String | Contact number |
| `whatsappNumber` | String | WhatsApp number |
| `imageUrl` | String | Profile photo URL |
| `availability` | String | `Available` / `Busy` / `Offline` |

### `requests` collection
| Field | Type | Description |
|---|---|---|
| `workerId` | String | Target worker's UID |
| `hirerId` | String | Requesting hirer's UID |
| `hirerName` | String | Hirer's display name |
| `status` | String | `Pending` / `Accepted` / `Declined` |
| `timestamp` | Long | Unix timestamp |

### `messages` collection
| Field | Type | Description |
|---|---|---|
| `senderId` | String | Sender's UID |
| `receiverId` | String | Receiver's UID |
| `text` | String | Message content |
| `timestamp` | Long | Unix timestamp |

---

## 🤝 Contributing

Contributions are welcome! Here's how to get started:

1. **Fork** the repository
2. **Create** a feature branch: `git checkout -b feature/your-feature-name`
3. **Commit** your changes with clear messages: `git commit -m "feat: add worker rating system"`
4. **Push** to your fork: `git push origin feature/your-feature-name`
5. **Open a Pull Request** with a description of your changes

### Commit Message Convention
```
feat:     New feature
fix:      Bug fix
ui:       UI / styling change
refactor: Code improvement without feature change
docs:     Documentation update
chore:    Build, config, dependency updates
```

---

## 🐛 Known Issues & Roadmap

- [ ] Push notifications for new hire requests and chat messages
- [ ] Worker ratings and reviews system
- [ ] Location-based filtering using GPS
- [ ] OTP / phone number authentication
- [ ] Hindi and Kannada language support
- [ ] Offline mode with cached worker profiles
- [ ] Admin dashboard for moderation

---

## 📄 License

```
MIT License

Copyright (c) 2024 Saniya Talikoti

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
```

---

## 👩‍💻 Author

<div align="center">

**Saniya Talikoti**

[![GitHub](https://img.shields.io/badge/GitHub-saniyatalikoti-181717?style=for-the-badge&logo=github)](https://github.com/saniyatalikoti)

*Built with ❤️ for the workers of Karnataka*

</div>

---

<div align="center">

⭐ **If this project helped you, please give it a star!** ⭐

</div>
