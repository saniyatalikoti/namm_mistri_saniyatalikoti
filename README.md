<div align="center">

<img src="https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white"/>
<img src="https://img.shields.io/badge/Language-Kotlin-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white"/>
<img src="https://img.shields.io/badge/UI-Jetpack%20Compose-4285F4?style=for-the-badge&logo=jetpackcompose&logoColor=white"/>
<img src="https://img.shields.io/badge/Architecture-MVVM-FF6F00?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Min%20SDK-API%2024-brightgreen?style=for-the-badge"/>
<img src="https://img.shields.io/badge/License-Educational-blue?style=for-the-badge"/>

<br/><br/>

# 🏗️ NammaMistri
### *Construction Work Made Simple*

> **NammaMistri** *(ನಮ್ಮ ಮಿಸ್ತ್ರಿ — meaning "Our Craftsman" in Kannada)* is an offline-first Android application built for contractors, site supervisors, and homeowners to manage construction projects end-to-end.

<br/>

[Features](#-features) • [Tech Stack](#️-tech-stack) • [Project Structure](#-project-structure) • [Installation](#️-installation--setup) • [Database Schema](#️-database-schema) • [Author](#-author)

</div>

---

## 📱 Overview

NammaMistri is a modern Android application built with **Kotlin** and **Jetpack Compose** that helps contractors and site managers:

- 📋 Track construction projects
- 👷 Manage workers and daily wages
- 💰 Monitor expenses in real time
- 🧱 Calculate material costs
- 📸 Capture and store site photos

All of this works **completely offline**, making it reliable even in areas with poor connectivity.

---

## ✨ Features

| Feature | Description |
|---|---|
| 📁 **Project Management** | Create and track multiple construction projects with status updates |
| 👷 **Worker Management** | Add workers, log daily attendance, track wages and advances |
| 🧱 **Material Calculator** | Estimate material quantities and costs for common construction needs |
| 💸 **Expense Tracker** | Record and categorize site expenses with date-wise history |
| 📸 **Photo Management** | Capture and store progress photos linked to each project |
| 📊 **Summary Dashboard** | View total labour cost, expenses, and project-level financial summary |
| 🌐 **English / Kannada Support** | Full bilingual UI for local accessibility |

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Language** | Kotlin 1.9.22 |
| **UI Framework** | Jetpack Compose + Material 3 |
| **Architecture** | MVVM (Model-View-ViewModel) |
| **Database** | Room (SQLite) 2.6.1 |
| **Async** | Kotlin Coroutines 1.7.3 + Flow |
| **Navigation** | Navigation Compose 2.7.7 |
| **Build System** | Gradle 8.2+ with KTS |

---

## 📂 Project Structure

```
NammaMistri/
├── app/
│   └── src/main/java/com/saniya/nammamistri/
│       ├── data/
│       │   ├── dao/                  # Room DAO interfaces
│       │   │   ├── ProjectDao.kt
│       │   │   ├── WorkerDao.kt
│       │   │   ├── MaterialDao.kt
│       │   │   ├── ExpenseDao.kt
│       │   │   └── PhotoDao.kt
│       │   ├── model/                # Entity data classes
│       │   │   ├── Project.kt
│       │   │   ├── Worker.kt
│       │   │   ├── Material.kt
│       │   │   ├── Expense.kt
│       │   │   └── Photo.kt
│       │   ├── repository/           # Data access layer
│       │   │   └── AppRepository.kt
│       │   └── AppDatabase.kt        # Room database instance
│       ├── ui/
│       │   ├── screens/              # Composable screens
│       │   │   ├── HomeScreen.kt
│       │   │   ├── ProjectScreen.kt
│       │   │   ├── WorkerScreen.kt
│       │   │   ├── MaterialScreen.kt
│       │   │   ├── ExpenseScreen.kt
│       │   │   ├── PhotoScreen.kt
│       │   │   └── SummaryScreen.kt
│       │   ├── viewmodel/            # ViewModels per feature
│       │   │   ├── ProjectViewModel.kt
│       │   │   ├── WorkerViewModel.kt
│       │   │   ├── MaterialViewModel.kt
│       │   │   └── ExpenseViewModel.kt
│       │   └── theme/                # Material 3 theming
│       │       ├── Color.kt
│       │       ├── Type.kt
│       │       └── Theme.kt
│       ├── utils/
│       │   ├── CurrencyFormatter.kt
│       │   └── DateUtils.kt
│       └── MainActivity.kt
├── gradle/
│   └── wrapper/
│       └── gradle-wrapper.properties
├── build.gradle.kts
├── settings.gradle.kts
└── README.md
```

---

## ✅ Prerequisites

Make sure you have the following installed before getting started:

- **Android Studio** Hedgehog (2023.1.1) or later
- **JDK** 17
- **Android SDK** API Level 24+ (Android 7.0 Nougat and above)
- **Kotlin** 1.9.x
- **Gradle** 8.2+
- **Git**

---

## 📦 Dependencies

```kotlin
// build.gradle.kts (app level)

plugins {
    alias(libs.plugins.android.application)
    alias(libs.plugins.kotlin.android)
    alias(libs.plugins.kotlin.compose)
    id("com.google.devtools.ksp")
}

dependencies {
    // Compose BOM
    implementation(platform("androidx.compose:compose-bom:2024.02.00"))
    implementation("androidx.compose.ui:ui")
    implementation("androidx.compose.ui:ui-tooling-preview")
    implementation("androidx.compose.material3:material3")
    implementation("androidx.activity:activity-compose:1.8.2")

    // Navigation
    implementation("androidx.navigation:navigation-compose:2.7.7")

    // Lifecycle & ViewModel
    implementation("androidx.lifecycle:lifecycle-runtime-ktx:2.7.0")
    implementation("androidx.lifecycle:lifecycle-viewmodel-compose:2.7.0")

    // Room
    implementation("androidx.room:room-runtime:2.6.1")
    implementation("androidx.room:room-ktx:2.6.1")
    ksp("androidx.room:room-compiler:2.6.1")

    // Coroutines
    implementation("org.jetbrains.kotlinx:kotlinx-coroutines-android:1.7.3")

    // Coil (Image Loading)
    implementation("io.coil-kt:coil-compose:2.5.0")

    // Testing
    testImplementation("junit:junit:4.13.2")
    androidTestImplementation("androidx.test.ext:junit:1.1.5")
    androidTestImplementation("androidx.compose.ui:ui-test-junit4")
}
```

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/saniyatalikoti/namm_mistri_saniyatalikoti.git
cd namm_mistri_saniyatalikoti
```

### 2. Open in Android Studio

```
File → Open → Select the cloned project folder
```

Wait for Gradle to sync and index the project.

### 3. Build the Project

```bash
./gradlew build
```

### 4. Run on Device or Emulator

- Connect an Android device with **USB Debugging** enabled, **or**
- Launch an emulator with API Level 24+

Then press ▶️ **Run** in Android Studio or:

```bash
./gradlew installDebug
```

---

## 🗄️ Database Schema

NammaMistri uses **Room** over SQLite with the following tables:

```kotlin
@Entity(tableName = "projects")
data class Project(
    @PrimaryKey(autoGenerate = true) val id: Int = 0,
    val name: String,
    val location: String,
    val startDate: String,
    val status: String           // "ongoing" | "completed" | "paused"
)

@Entity(tableName = "workers")
data class Worker(
    @PrimaryKey(autoGenerate = true) val id: Int = 0,
    val projectId: Int,
    val name: String,
    val role: String,
    val wage: Double,            // Daily wage in ₹
    val daysWorked: Int,
    val advance: Double          // Advance amount paid
)

@Entity(tableName = "materials")
data class Material(
    @PrimaryKey(autoGenerate = true) val id: Int = 0,
    val projectId: Int,
    val name: String,
    val quantity: Double,
    val unit: String,            // "bags" | "cubic ft" | "sq ft" etc.
    val pricePerUnit: Double
)

@Entity(tableName = "expenses")
data class Expense(
    @PrimaryKey(autoGenerate = true) val id: Int = 0,
    val projectId: Int,
    val description: String,
    val amount: Double,
    val date: String,
    val category: String         // "transport" | "tools" | "misc" etc.
)

@Entity(tableName = "photos")
data class Photo(
    @PrimaryKey(autoGenerate = true) val id: Int = 0,
    val projectId: Int,
    val filePath: String,
    val caption: String,
    val dateTaken: String
)
```

---

## 📊 Summary Computation

The summary dashboard computes project financials as follows:

```kotlin
data class ProjectSummary(
    val totalWorkers: Int,
    val labourCost: Double,
    val totalMaterialCost: Double,
    val totalExpenses: Double,
    val grandTotal: Double
)

fun computeSummary(
    workers: List<Worker>,
    materials: List<Material>,
    expenses: List<Expense>
): ProjectSummary {
    val totalWorkers = workers.size

    // Net labour cost after deducting advances
    val labourCost = workers.sumOf { (it.wage * it.daysWorked) - it.advance }

    // Total material cost from quantity × unit price
    val totalMaterialCost = materials.sumOf { it.quantity * it.pricePerUnit }

    // Sum of all miscellaneous expenses
    val totalExpenses = expenses.sumOf { it.amount }

    // Grand total across all cost heads
    val grandTotal = labourCost + totalMaterialCost + totalExpenses

    return ProjectSummary(
        totalWorkers = totalWorkers,
        labourCost = labourCost,
        totalMaterialCost = totalMaterialCost,
        totalExpenses = totalExpenses,
        grandTotal = grandTotal
    )
}
```

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

```bash
# 1. Fork the repository on GitHub

# 2. Create your feature branch
git checkout -b feature/your-feature-name

# 3. Commit your changes
git commit -m "feat: add your feature description"

# 4. Push to your fork
git push origin feature/your-feature-name

# 5. Open a Pull Request on GitHub
```

Please ensure your code follows **Kotlin coding conventions** and includes relevant comments.

---

## 📄 License

This project is built for **educational and learning purposes**.  
Feel free to use it as a reference for building offline-first Android apps with Jetpack Compose and Room.

---

## 👩‍💻 Author

<div align="center">

**Saniya Talikoti**

*BE in Computer Science Engineering*  
Android Developer • Kotlin Learner • Construction Tech Enthusiast

[![GitHub](https://img.shields.io/badge/GitHub-saniyatalikoti-181717?style=for-the-badge&logo=github)](https://github.com/saniyatalikoti)

</div>

---

<div align="center">
  <sub>Made with ❤️ for the construction community of Karnataka</sub>
</div>
