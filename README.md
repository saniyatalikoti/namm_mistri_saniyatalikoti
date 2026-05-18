# 🏗️ NammaMistri

### Construction Work Made Simple

*NammaMistri is a modern Android application built with Kotlin and Jetpack Compose that helps contractors and site managers track construction projects, manage workers, monitor expenses, and calculate material costs — all in one place.*

## 📋 Table of Contents

* Overview
* Features
* Screenshots
* Tech Stack
* Project Structure
* Prerequisites
* Dependencies
* Installation & Setup
* Database Schema
* Summary Computation
* Contributing
* License
* Author

## 📱 Overview

**NammaMistri** (meaning *Our Craftsman* in Kannada) is an offline-first construction site management Android application built for contractors, site supervisors, and homeowners.

## ✨ Features

* Project management
* Worker management
* Material calculator
* Expense tracker
* Photo management
* Summary dashboard
* English/Kannada support

## 📸 Screenshots

## 🛠️ Tech Stack

Kotlin, Jetpack Compose, Room, MVVM, Coroutines, Navigation Compose, Material 3

## 📂 Project Structure

```text
NammaMistri/
├── app/
│   ├── src/main/java/com/saniya/nammamistri/
│   │   ├── data/
│   │   ├── ui/
│   │   ├── utils/
│   │   └── MainActivity.kt
├── gradle/
├── build.gradle.kts
├── settings.gradle.kts
└── README.md
```

## ✅ Prerequisites

Android Studio Hedgehog, JDK 17, Android SDK API 24+, Kotlin 1.9.x, Gradle 8.2+, Git

## 📦 Dependencies

Includes Kotlin 1.9.22, AGP 8.2.2, Compose BOM 2024.02.00, Navigation 2.7.7, Room 2.6.1, Coroutines 1.7.3.

## ⚙️ Installation & Setup

```bash
git clone https://github.com/saniyatalikoti/namm_mistri_saniyatalikoti.git
cd namm_mistri_saniyatalikoti
./gradlew build
```

## 🗄️ Database Schema

Projects, Workers, Materials, Expenses, Photos tables with Room SQLite.

## 📊 Summary Computation

```kotlin
val totalWorkers = workers.size
val labourCost = workers.sumOf { (it.wage * it.daysWorked) - it.advance }
val totalExpenses = expenses.sumOf { it.amount }
val finalTotal = labourCost + totalExpenses
```

## 🤝 Contributing

Fork → Branch → Commit → Push → Pull Request

## 📄 License

Educational and learning purposes.

## 👩‍💻 Author

### Saniya Talikoti

BE in Computer Science Engineering Android Developer • Kotlin Learner • Construction Tech Enthusiast
