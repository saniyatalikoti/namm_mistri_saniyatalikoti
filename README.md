<div align="center">

<h1>🏗️ NammaMistri</h1>

<p><strong>Bilingual Construction Management App for Masons & Contractors</strong></p>

<p><em>NammaMistri is a modern Android application built with Kotlin and Jetpack Compose that helps masons and contractors efficiently manage construction projects, workers, attendance, expenses, and progress tracking — all in one offline-first mobile solution.</em></p>

<br/>

<img src="https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" />
<img src="https://img.shields.io/badge/Language-Kotlin-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white" />
<img src="https://img.shields.io/badge/UI-Jetpack%20Compose-4285F4?style=for-the-badge&logo=jetpackcompose&logoColor=white" />
<img src="https://img.shields.io/badge/Database-Room-1976D2?style=for-the-badge" />
<img src="https://img.shields.io/badge/Architecture-MVVM-FF6F00?style=for-the-badge" />
<img src="https://img.shields.io/badge/Language%20Support-English%20%7C%20Kannada-success?style=for-the-badge" />
<img src="https://img.shields.io/badge/Status-Active-00C853?style=for-the-badge" />

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Installation & Setup](#️-installation--setup)
- [Future Enhancements](#-future-enhancements)
- [Author](#-author)

---

## 📱 Overview

**NammaMistri** is a bilingual **English + Kannada construction management Android application** designed specifically for **masons, contractors, and small construction teams**.

The app simplifies daily construction site management by enabling users to:

- Manage multiple construction projects
- Add and track workers per project
- Record daily worker attendance
- Track labour and other expenses
- Store project photos locally
- Monitor project progress and total cost
- Switch seamlessly between English and Kannada languages

Built with a clean offline-first architecture, NammaMistri ensures smooth performance without dependency on cloud connectivity.

---

## ✨ Features

### 🏗️ Project Management
- Create, edit, search, and delete construction projects
- Confirmed cascade delete for safe removal
- Track project progress with dashboard summary
- Readable project creation date display

### 👷 Worker Management
- Add workers to specific projects
- Manage worker details efficiently
- Associate labour charges per worker

### 📅 Attendance Tracking
- Insert daily worker attendance
- Update attendance records
- Maintain attendance history per project

### 💰 Expense Management
- Add project expenses
- Track expense categories
- Automatically calculate total project expenses

### 📸 Photo Storage
- Store project progress images locally using URI storage
- View saved construction site photos anytime

### 📊 Smart Dashboard
- Project progress tracking
- Labour cost calculation
- Expense total calculation
- Final total cost summary

### 🌐 Multi-language Support
- Full in-app language switching
- English UI support
- Kannada UI support
- Compose-based dynamic localization

---

## 🛠️ Tech Stack

| Layer | Technology |
|------|------------|
| Language | Kotlin |
| UI Toolkit | Jetpack Compose Material 3 |
| Architecture | MVVM |
| Local Database | Room Database |
| Async Operations | Kotlin Coroutines |
| Image Storage | Local URI Storage |
| State Management | ViewModel + State |
| IDE | Android Studio |

---

## 🏗️ Architecture

NammaMistri follows the **MVVM (Model–View–ViewModel)** architecture for clean separation of concerns.

```text
UI Layer (Compose Screens)
        │
        ▼
ViewModel Layer
        │
        ▼
Repository Layer
        │
        ▼
Room Database (Local Storage)
