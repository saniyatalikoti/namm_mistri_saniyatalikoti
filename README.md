<div align="center">

<h1>🏗️ NammaMistri</h1>

<p><strong>Construction Work Made Simple</strong></p>

<p><em>NammaMistri is a modern Android application built with Kotlin and Jetpack Compose that helps contractors and site managers track construction projects, manage workers, monitor expenses, and calculate material costs — all in one place.</em></p>

<br/>

<img src="https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" />
<img src="https://img.shields.io/badge/Language-Kotlin-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white" />
<img src="https://img.shields.io/badge/UI-Jetpack%20Compose-4285F4?style=for-the-badge&logo=jetpackcompose&logoColor=white" />
<img src="https://img.shields.io/badge/Storage-Room%20DB-FF6F00?style=for-the-badge&logo=sqlite&logoColor=white" />
<img src="https://img.shields.io/badge/Status-Active-00C853?style=for-the-badge" />
<img src="https://img.shields.io/badge/Min%20SDK-24-blue?style=for-the-badge" />
<img src="https://img.shields.io/badge/Bilingual-EN%20%7C%20KN-orange?style=for-the-badge" />

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Screenshots](#-screenshots)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Dependencies](#-dependencies)
- [Installation & Setup](#️-installation--setup)
- [Database Schema](#️-database-schema)
- [Future Enhancements](#-future-enhancements)
- [Contributing](#-contributing)
- [License](#-license)
- [Author](#-author)

---

## 📱 Overview

**NammaMistri** (meaning *"Our Craftsman"* in Kannada) is an offline-first construction site management app built for contractors, site supervisors, and homeowners managing building projects in Karnataka and beyond.

It centralises everything a site manager needs day-to-day:

- **Projects** — create and track multiple construction projects with day-based progress
- **Workers** — log wage, advance, and days worked; auto-calculate net labour cost per worker
- **Materials** — calculate bricks, cement bags, and sand loads needed for any wall with live cost estimation
- **Expenses** — record and categorise all site expenditures
- **Photos** — attach progress photos directly to each project
- **Summary** — single-screen financial overview with progress bar, labour cost, total expenses, and final total

The app runs fully **offline using Room (SQLite)** — no sign-in required, no internet needed, data stays on your device. It also supports **Kannada language** alongside English for local usability.

---

## ✨ Features

### 📁 Project Management
- Create construction projects with a name and total day estimate
- Search across all your projects instantly
- Open, edit, or delete any project
- Visual **progress bar** showing completed vs remaining days
- Per-project tabs: Materials, Workers, Expenses, Photos, Summary

### 👷 Worker Tracking
- Add workers per project with daily wage and advance paid
- Log **days worked** and auto-calculate net labour cost (wage × days − advance)
- View running totals of labour cost across all workers in a project

### 🧱 Material Calculator
- Input wall dimensions (length, height, thickness in inches)
- Set rates for bricks, cement bags, and sand per load
- Instantly calculates **wall volume, bricks required, cement bags, sand loads, and total material cost**
- Eliminates manual estimation errors on site

### 💸 Expense Tracker
- Add categorised expenses with title and amount
- Scrollable list of all recorded expenses per project
- Feeds directly into the project Summary

### 📸 Photo Log
- Attach site progress photos to each project
- Pick photos from device gallery using the system photo picker
- "No photos yet" placeholder state when empty

### 📊 Project Summary
- Project metadata: creation date, total days, progress percentage
- Live financial totals: workers, labour cost, total expenses, **final total**
- Update completed days directly from the Summary tab
- All figures recalculate in real time on save

### 🌐 Bilingual Support
- Toggle between **English** and **Kannada** from any screen via the Language button in the header
- Localised UI strings for all major labels and actions

---

## 📸 Screenshots

<div align="center">

<table>
  <tr>
    <td align="center"><b>Projects Dashboard</b></td>
    <td align="center"><b>Worker Management</b></td>
    <td align="center"><b>Material Calculator</b></td>
  </tr>
  <tr>
    <td><img src="screenshots/01_projects_dashboard.png" width="220"/></td>
    <td><img src="screenshots/02_worker_management.png" width="220"/></td>
    <td><img src="screenshots/03_material_calculator.png" width="220"/></td>
  </tr>
  <tr>
    <td align="center"><b>Expense Tracker</b></td>
    <td align="center"><b>Photo Log</b></td>
    <td align="center"><b>Project Summary</b></td>
  </tr>
  <tr>
    <td><img src="screenshots/04_expense_tracker.png" width="220"/></td>
    <td><img src="screenshots/05_photo_log.png" width="220"/></td>
    <td><img src="screenshots/06_project_summary.png" width="220"/></td>
  </tr>
</table>

</div>

> **To add screenshots to your repo:**
> 1. Create a `screenshots/` folder at the root of the repository
> 2. Save the 6 app screenshots with the filenames used above
> 3. Push to GitHub — the images will appear here automatically

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Language | Kotlin |
| UI Toolkit | Jetpack Compose (Material 3) |
| Local Storage | Room (SQLite) |
| Architecture | MVVM + Repository Pattern |
| Async / Concurrency | Kotlin Coroutines + Flow |
| Image Picker | Android Photo Picker API |
| Navigation | Jetpack Navigation Compose |
| Localisation | Android String Resources (EN + KN) |
| Build System | Gradle (Kotlin DSL) |
| IDE | Android Studio Hedgehog+ |

---

## 📂 Project Structure

```
NammaMistri/
│
├── app/
│   ├── src/
│   │   └── main/
│   │       ├── java/com/saniya/nammamistri/
│   │       │   │
│   │       │   ├── MainActivity.kt                   # App entry point, NavHost setup
│   │       │   │
│   │       │   ├── ui/
│   │       │   │   ├── theme/
│   │       │   │   │   ├── Color.kt
│   │       │   │   │   ├── Theme.kt
│   │       │   │   │   └── Type.kt
│   │       │   │   │
│   │       │   │   ├── project/                      # Project screens
│   │       │   │   │   ├── ProjectListScreen.kt      # Dashboard — add + search + list
│   │       │   │   │   ├── ProjectDetailScreen.kt    # Tabs: Materials, Workers, Expenses…
│   │       │   │   │   └── ProjectViewModel.kt
│   │       │   │   │
│   │       │   │   ├── worker/                       # Worker tracking screens
│   │       │   │   │   ├── WorkerScreen.kt           # Add worker, list, days worked
│   │       │   │   │   └── WorkerViewModel.kt
│   │       │   │   │
│   │       │   │   ├── material/                     # Material calculator screen
│   │       │   │   │   ├── MaterialScreen.kt         # Inputs + live calculation summary
│   │       │   │   │   └── MaterialViewModel.kt
│   │       │   │   │
│   │       │   │   ├── expense/                      # Expense tracker screen
│   │       │   │   │   ├── ExpenseScreen.kt          # Add + list expenses
│   │       │   │   │   └── ExpenseViewModel.kt
│   │       │   │   │
│   │       │   │   ├── photo/                        # Photo log screen
│   │       │   │   │   ├── PhotoScreen.kt            # Pick photo + gallery view
│   │       │   │   │   └── PhotoViewModel.kt
│   │       │   │   │
│   │       │   │   └── summary/                      # Project summary screen
│   │       │   │       ├── SummaryScreen.kt          # Progress + financials + update days
│   │       │   │       └── SummaryViewModel.kt
│   │       │   │
│   │       │   ├── data/
│   │       │   │   ├── model/                        # Room entity / data classes
│   │       │   │   │   ├── Project.kt
│   │       │   │   │   ├── Worker.kt
│   │       │   │   │   ├── Material.kt
│   │       │   │   │   ├── Expense.kt
│   │       │   │   │   └── Photo.kt
│   │       │   │   │
│   │       │   │   ├── dao/                          # Room DAO interfaces
│   │       │   │   │   ├── ProjectDao.kt
│   │       │   │   │   ├── WorkerDao.kt
│   │       │   │   │   ├── MaterialDao.kt
│   │       │   │   │   ├── ExpenseDao.kt
│   │       │   │   │   └── PhotoDao.kt
│   │       │   │   │
│   │       │   │   ├── database/
│   │       │   │   │   └── AppDatabase.kt            # Room database singleton
│   │       │   │   │
│   │       │   │   └── repository/                   # Data access abstraction
│   │       │   │       ├── ProjectRepository.kt
│   │       │   │       ├── WorkerRepository.kt
│   │       │   │       ├── MaterialRepository.kt
│   │       │   │       ├── ExpenseRepository.kt
│   │       │   │       └── PhotoRepository.kt
│   │       │   │
│   │       │   └── utils/                            # Helpers & constants
│   │       │       ├── Constants.kt
│   │       │       ├── CurrencyFormatter.kt
│   │       │       └── NavRoutes.kt
│   │       │
│   │       └── res/
│   │           ├── drawable/
│   │           ├── mipmap/
│   │           └── values/
│   │               ├── strings.xml                   # English strings
│   │               └── values-kn/
│   │                   └── strings.xml               # Kannada strings
│   │
│   └── build.gradle.kts
│
├── gradle/
│   └── libs.versions.toml
├── screenshots/                                      # ← Add your 6 screenshots here
├── build.gradle.kts
├── settings.gradle.kts
└── README.md
```

---

## ✅ Prerequisites

Before you begin, ensure you have the following installed:

| Tool | Minimum Version | Download |
|---|---|---|
| Android Studio | Hedgehog (2023.1.1) | [Download](https://developer.android.com/studio) |
| JDK | 17 | Bundled with Android Studio |
| Android SDK | API 24 (min) / API 34 (target) | Via SDK Manager |
| Kotlin | 1.9.x | Bundled with Android Studio |
| Gradle | 8.2+ | Auto-downloaded via wrapper |
| Git | Latest | [Download](https://git-scm.com) |

> **No Firebase account or internet connection needed** — NammaMistri is fully offline and requires no backend services.

---

## 📦 Dependencies

All versions are managed centrally in `gradle/libs.versions.toml`.

### Core Android
```toml
[versions]
kotlin            = "1.9.22"
agp               = "8.2.2"
core-ktx          = "1.12.0"
lifecycle         = "2.7.0"
activity-compose  = "1.8.2"

[libraries]
androidx-core-ktx     = { module = "androidx.core:core-ktx",                        version.ref = "core-ktx" }
lifecycle-runtime-ktx = { module = "androidx.lifecycle:lifecycle-runtime-ktx",      version.ref = "lifecycle" }
lifecycle-viewmodel   = { module = "androidx.lifecycle:lifecycle-viewmodel-compose", version.ref = "lifecycle" }
activity-compose      = { module = "androidx.activity:activity-compose",            version.ref = "activity-compose" }
```

### Jetpack Compose (BOM)
```toml
[versions]
compose-bom = "2024.02.00"

[libraries]
compose-bom            = { module = "androidx.compose:compose-bom",            version.ref = "compose-bom" }
compose-ui             = { module = "androidx.compose.ui:ui" }
compose-ui-graphics    = { module = "androidx.compose.ui:ui-graphics" }
compose-ui-tooling     = { module = "androidx.compose.ui:ui-tooling-preview" }
compose-material3      = { module = "androidx.compose.material3:material3" }
compose-icons-extended = { module = "androidx.compose.material:material-icons-extended" }
```

### Navigation
```toml
[versions]
navigation-compose = "2.7.7"

[libraries]
navigation-compose = { module = "androidx.navigation:navigation-compose", version.ref = "navigation-compose" }
```

### Room (Local Database)
```toml
[versions]
room = "2.6.1"

[libraries]
room-runtime  = { module = "androidx.room:room-runtime",  version.ref = "room" }
room-ktx      = { module = "androidx.room:room-ktx",      version.ref = "room" }
room-compiler = { module = "androidx.room:room-compiler", version.ref = "room" }
```

### Coroutines
```toml
[versions]
coroutines = "1.7.3"

[libraries]
coroutines-core    = { module = "org.jetbrains.kotlinx:kotlinx-coroutines-core",    version.ref = "coroutines" }
coroutines-android = { module = "org.jetbrains.kotlinx:kotlinx-coroutines-android", version.ref = "coroutines" }
```

### `app/build.gradle.kts` — Dependencies Block
```kotlin
dependencies {
    // Core
    implementation(libs.androidx.core.ktx)
    implementation(libs.lifecycle.runtime.ktx)
    implementation(libs.lifecycle.viewmodel)
    implementation(libs.activity.compose)

    // Compose BOM
    implementation(platform(libs.compose.bom))
    implementation(libs.compose.ui)
    implementation(libs.compose.ui.graphics)
    implementation(libs.compose.ui.tooling)
    implementation(libs.compose.material3)
    implementation(libs.compose.icons.extended)

    // Navigation
    implementation(libs.navigation.compose)

    // Room
    implementation(libs.room.runtime)
    implementation(libs.room.ktx)
    ksp(libs.room.compiler)              // or kapt if not using KSP

    // Coroutines
    implementation(libs.coroutines.core)
    implementation(libs.coroutines.android)

    // Testing
    testImplementation("junit:junit:4.13.2")
    androidTestImplementation("androidx.test.ext:junit:1.1.5")
    androidTestImplementation("androidx.test.espresso:espresso-core:3.5.1")
    androidTestImplementation(platform(libs.compose.bom))
    androidTestImplementation("androidx.compose.ui:ui-test-junit4")
    debugImplementation("androidx.compose.ui:ui-tooling")
}
```

---

## ⚙️ Installation & Setup

### Step 1 — Clone the Repository
```bash
git clone https://github.com/saniyatalikoti/namm_mistri_saniyatalikoti.git
cd namm_mistri_saniyatalikoti
```

### Step 2 — Open in Android Studio
1. Launch **Android Studio**
2. Select **File → Open** and choose the project folder
3. Wait for the IDE to index the project and Gradle to sync

### Step 3 — Sync Gradle
Click **"Sync Now"** in the notification bar, or run:
```bash
./gradlew build
```

### Step 4 — Run the App
- Connect a physical Android device (API 24+) via USB with Developer Options enabled, **or**
- Start an Android Virtual Device (AVD) from **Device Manager → Create Device**
- Press **Run ▶** (Shift + F10)

> No internet connection or backend setup needed — the app is entirely offline.

---

## 🗄️ Database Schema

NammaMistri uses **Room (SQLite)** for all local persistence. Below is the complete entity schema.

> All tables use `projectId` as a foreign key so deleting a project cascades to all its workers, materials, expenses, and photos automatically.

---

### `projects` table

```
projects
├── id            INTEGER  PRIMARY KEY AUTOINCREMENT
├── name          TEXT     NOT NULL
├── totalDays     INTEGER  NOT NULL
├── completedDays INTEGER  DEFAULT 0
└── createdAt     TEXT     NOT NULL     -- ISO-8601 date string
```

---

### `workers` table

```
workers
├── id         INTEGER  PRIMARY KEY AUTOINCREMENT
├── projectId  INTEGER  NOT NULL  REFERENCES projects(id) ON DELETE CASCADE
├── name       TEXT     NOT NULL
├── wage       REAL     NOT NULL  -- daily wage in ₹
├── advance    REAL     DEFAULT 0 -- advance paid in ₹
└── daysWorked INTEGER  DEFAULT 0
```

**Computed field (ViewModel, not stored):**
```
labourCost = (wage × daysWorked) - advance
```

---

### `materials` table

```
materials
├── id             INTEGER  PRIMARY KEY AUTOINCREMENT
├── projectId      INTEGER  NOT NULL  REFERENCES projects(id) ON DELETE CASCADE
├── wallLength     REAL     NOT NULL  -- feet
├── wallHeight     REAL     NOT NULL  -- feet
├── wallThickness  REAL     NOT NULL  -- inches
├── brickRate      REAL     NOT NULL  -- ₹ per brick
├── cementRate     REAL     NOT NULL  -- ₹ per bag
└── sandRate       REAL     NOT NULL  -- ₹ per load
```

**Calculated outputs (ViewModel):**
```
wallVolume   = length × height × (thickness ÷ 12)     -- cubic feet
bricksNeeded = wallVolume × 13.5                       -- standard estimation
cementBags   = wallVolume ÷ 10
sandLoads    = wallVolume ÷ 400
materialCost = (bricks × brickRate) + (cement × cementRate) + (sand × sandRate)
```

---

### `expenses` table

```
expenses
├── id        INTEGER  PRIMARY KEY AUTOINCREMENT
├── projectId INTEGER  NOT NULL  REFERENCES projects(id) ON DELETE CASCADE
├── title     TEXT     NOT NULL
└── amount    REAL     NOT NULL
```

---

### `photos` table

```
photos
├── id        INTEGER  PRIMARY KEY AUTOINCREMENT
├── projectId INTEGER  NOT NULL  REFERENCES projects(id) ON DELETE CASCADE
└── photoUri  TEXT     NOT NULL  -- local content URI from Android photo picker
```

---

### Summary Computation

All summary figures are computed live in `SummaryViewModel` by querying across tables:

```kotlin
val totalWorkers  = workers.size
val labourCost    = workers.sumOf { (it.wage * it.daysWorked) - it.advance }
val totalExpenses = expenses.sumOf { it.amount }
val finalTotal    = labourCost + totalExpenses
val progressPct   = (project.completedDays.toFloat() / project.totalDays) * 100f
```

---

## 📈 Future Enhancements

| Feature | Description |
|---|---|
| 🔔 Daily Reminders | Local notifications to update days worked each evening |
| 📤 Export to PDF | Generate shareable project reports as PDFs |
| 📍 Site Location | Attach GPS coordinates or an address to each project |
| 📊 Charts & Analytics | Visual expense breakdown and labour cost trends |
| ☁️ Cloud Backup | Optional Firebase sync for cross-device access |
| 🔒 PIN / Biometric Lock | Protect sensitive financial data with app-level security |
| 🌐 More Languages | Telugu, Tamil, and Hindi localisation |
| 🖼️ Photo Gallery View | Full-screen swipeable image viewer for site photos |

---

## 🤝 Contributing

Contributions are welcome and appreciated!

1. **Fork** the repository
2. **Create** a feature branch
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Commit** your changes with a descriptive message
   ```bash
   git commit -m "feat: add PDF export for project summary"
   ```
4. **Push** to your branch
   ```bash
   git push origin feature/your-feature-name
   ```
5. **Open** a Pull Request against `main`

Please follow Kotlin coding conventions and Jetpack Compose best practices. Include a brief description of your changes in the PR.

---

## 📄 License

This project is developed for educational and learning purposes. All rights reserved by the author.

---

## 👩‍💻 Author

<div align="center">

### Saniya Talikoti
**BE in Computer Science Engineering**

Android Developer · Kotlin Learner · Construction Tech Enthusiast

[![GitHub](https://img.shields.io/badge/GitHub-saniyatalikoti-181717?style=for-the-badge&logo=github)](https://github.com/saniyatalikoti)

</div>

---

<div align="center">
  <sub>If you found this project helpful, please consider giving it a ⭐ on GitHub!</sub>
</div>
