<div align="center">

# 🏗️ NammaMistri

### Construction Work Made Simple

*NammaMistri is a modern Android application built with Kotlin and Jetpack Compose that helps contractors and site managers track construction projects, manage workers, monitor expenses, and calculate material costs — all in one place.*

<img src="https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" />
<img src="https://img.shields.io/badge/Language-Kotlin-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white" />
<img src="https://img.shields.io/badge/UI-Jetpack%20Compose-4285F4?style=for-the-badge&logo=jetpackcompose&logoColor=white" />
<img src="https://img.shields.io/badge/Storage-Room%20DB-FF6F00?style=for-the-badge&logo=sqlite&logoColor=white" />
<img src="https://img.shields.io/badge/Status-Active-00C853?style=for-the-badge" />
<img src="https://img.shields.io/badge/Min%20SDK-24-blue?style=for-the-badge" />
<img src="https://img.shields.io/badge/Bilingual-EN%20%7C%20KN-orange?style=for-the-badge" />

</div>

---

# 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Screenshots](#screenshots)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Database Schema](#database-schema)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

---

# 📱 Overview

**NammaMistri** is a bilingual English and Kannada Android application designed for contractors, builders, and site supervisors to efficiently manage construction projects.

The app helps users:

- Manage multiple projects
- Track worker attendance and wages
- Calculate construction materials
- Record daily expenses
- Store project progress photos
- View project summary reports

Built entirely with **Kotlin + Jetpack Compose + Room Database**, the application works offline without requiring internet connectivity.

---

# ✨ Features

## 📁 Project Management
- Add new construction projects
- Edit and delete projects
- Search projects instantly
- Progress tracking with visual progress bar

## 👷 Worker Management
- Add workers per project
- Record daily wage
- Track advance payments
- Update days worked
- Auto-calculate labour cost

## 🧱 Material Calculator
Calculate:
- Bricks required
- Cement bags
- Sand loads
- Total material cost

Based on:
- Wall length
- Height
- Thickness
- Material rates

## 💸 Expense Tracker
- Add expenses
- Categorize costs
- View total expenses instantly

## 📸 Photo Management
- Add construction progress photos
- Store project-specific image records

## 📊 Summary Dashboard
Shows:
- Total workers
- Labour cost
- Total expenses
- Project progress
- Final total estimate

## 🌐 Language Support
Supports:
- English
- Kannada

---

# 📸 Screenshots

<div align="center">

<table>
  <tr>
    <td align="center"><b>Projects Dashboard</b></td>
    <td align="center"><b>Worker Management</b></td>
    <td align="center"><b>Material Calculator</b></td>
  </tr>
  <tr>
    <td>
      <img src="https://github.com/user-attachments/assets/eb9806a9-e103-4895-8c1b-36cbecc9969c" width="220"/>
    </td>
    <td>
      <img src="https://github.com/user-attachments/assets/93eae877-fbc3-4ae4-9b5c-a7562cbcb8f3" width="220"/>
    </td>
    <td>
      <img src="https://github.com/user-attachments/assets/fbd2f5e3-c3e0-4129-b8f7-f96584de6302" width="220"/>
    </td>
  </tr>

  <tr>
    <td align="center"><b>Expense Tracker</b></td>
    <td align="center"><b>Photo Log</b></td>
    <td align="center"><b>Project Summary</b></td>
  </tr>
  <tr>
    <td>
      <img src="https://github.com/user-attachments/assets/ad52d7d4-3a30-4f55-9674-42f576116b92" width="220"/>
    </td>
    <td>
      <img src="https://github.com/user-attachments/assets/54c4f5d6-8841-4432-ae38-45679160670f" width="220"/>
    </td>
    <td>
      <img src="https://github.com/user-attachments/assets/16ac1c2a-0c1e-4c76-9097-ae3c4d47d6b5" width="220"/>
    </td>
  </tr>
</table>

</div>

---

# 🛠️ Tech Stack

| Technology | Usage |
|----------|-------|
| Kotlin | Programming Language |
| Jetpack Compose | UI Development |
| Room Database | Local Storage |
| MVVM Architecture | App Architecture |
| Coroutines | Async Operations |
| Navigation Compose | Screen Navigation |
| Material 3 | UI Components |

---

# 📂 Project Structure

```text
NammaMistri/
│
├── app/
│   ├── src/main/java/com/saniya/nammamistri/
│   │   ├── data/
│   │   │   ├── dao/
│   │   │   ├── database/
│   │   │   ├── model/
│   │   │   └── repository/
│   │   │
│   │   ├── ui/
│   │   │   ├── project/
│   │   │   ├── worker/
│   │   │   ├── material/
│   │   │   ├── expense/
│   │   │   ├── photo/
│   │   │   ├── summary/
│   │   │   └── theme/
│   │   │
│   │   ├── utils/
│   │   └── MainActivity.kt
│   │
│   └── res/
│       ├── drawable/
│       ├── mipmap/
│       └── values/
│
├── gradle/
├── build.gradle.kts
├── settings.gradle.kts
└── README.md
