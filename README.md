# HitAlert - Accident Detection & Prevention System 🚨📱

**Real-time IoT-based accident detection with intelligent alerts and GPS location tracking**

> Built in 2022 before AI-assisted development tools became common, this project focuses on real-time accident detection, alert generation & GPS-based location tracking using IoT hardware & a Flutter mobile application.

## 🏆 Recognition

**SSIP Grant Award:** ₹16,000 received for innovation and implementation in accident detection technology.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Architecture](#project-architecture)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running the App](#running-the-app)
- [Project Structure](#project-structure)
- [Core Modules](#core-modules)
- [IoT Hardware Integration](#iot-hardware-integration)
- [API Integration](#api-integration)
- [Contributing](#contributing)
- [License](#license)

---

## 🎯 Overview

**HitAlert** is a comprehensive accident detection and prevention system that combines IoT sensors with a mobile application to provide real-time monitoring, instant alerts, and emergency response coordination.

The system detects accidents through multiple sensor inputs (flame detection, smoke detection, temperature monitoring, alcohol detection) and immediately alerts nearby hospitals and fire stations with GPS coordinates of the incident location.

---

## ✨ Features

### 🔴 Accident Detection
- **Flame Detection** - Real-time fire/flame detection using IoT sensors
- **Smoke Detection** - Early warning system for smoke/hazardous fumes
- **Temperature Monitoring** - High-temperature alerts for industrial/vehicle accidents
- **Alcohol Detection (MQ3 Sensor)** - Detection of alcohol presence on vehicle occupants
- **Air Quality Monitoring (MQ4 Sensor)** - Detection of hazardous gases

### 📍 Location & Response
- **GPS-based Location Tracking** - Real-time accident location identification
- **Emergency Alerts** - Instant notification to nearby hospitals and fire stations
- **SOS Broadcast** - Emergency signal distribution to emergency services

### 📱 Mobile App Features
- **User Authentication** - Secure login/registration system with OTP verification
- **Dashboard** - Real-time sensor data visualization and status monitoring
- **Emergency Contacts** - Quick access to nearby hospitals and fire stations
- **Settings & Preferences** - User-customizable alert thresholds and preferences
- **FAQs & Documentation** - Built-in help system with frequently asked questions
- **Terms & Conditions** - Legal compliance documentation

### 🔐 Security Features
- **OTP-based Verification** - Enhanced security for account recovery
- **Secure Data Storage** - Local encrypted storage using SharedPreferences
- **Role-based Access** - Different access levels for different user types

---

## 🛠 Tech Stack

### Frontend
- **Framework:** Flutter 2.18.6+
- **Language:** Dart
- **UI Libraries:**
  - HexColor (^2.0.4) - Color management
  - Font Awesome Flutter (^9.1.0) - Icons
  - Animated Splash Screen (^1.1.0) - Splash screens
  - Cupertino Icons (^1.0.2) - iOS-style icons

### Backend & Communication
- **HTTP Client:** http (^0.13.3) - REST API communication
- **Local Storage:** shared_preferences (^2.1.0) - User data persistence
- **Notifications:** FlutterToast (8.0.8) - User feedback messages

### IoT & Hardware
- **Sensors Supported:**
  - Flame Sensors
  - Smoke Sensors (MQ-2, MQ-5)
  - Temperature Sensors (DHT11, LM35)
  - Alcohol Sensor (MQ-3)
  - Gas Sensor (MQ-4)
- **Microcontroller:** Arduino/NodeMCU compatible

### Platform Support
- **Android:** SDK 21+ with Material Design
- **iOS:** iOS 11.0+
- **Web:** Planned support

---

## 🏗 Project Architecture

```
HitAlert System Architecture
│
├── IoT Hardware Layer
│   ├── Flame Detection Sensor
│   ├── Smoke Detection Sensor (MQ Series)
│   ├── Temperature Sensor
│   ├── Alcohol Detection (MQ-3)
│   ├── Gas Detection (MQ-4)
│   └── GPS Module
│
├── Microcontroller (Arduino/NodeMCU)
│   ├── Sensor Data Processing
│   ├── Real-time Monitoring
│   └── HTTP API Communication
│
├── Flutter Mobile Application
│   ├── Authentication Module
│   ├── Dashboard (Real-time Monitoring)
│   ├── Alert Management
│   ├── Location Services
│   ├── Emergency Contacts
│   └── User Settings
│
└── Backend Services
    ├── User Management API
    ├── Alert Distribution System
    ├── Hospital/Fire Station Database
    └── Location Tracking Service
```

---

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

- **Flutter SDK** (2.18.6+) - [Download](https://flutter.dev/docs/get-started/install)
- **Dart SDK** (Included with Flutter)
- **Android Studio** or **Xcode** (for mobile platform)
- **Git** - Version control
- **Android Device** or **Emulator** / **iOS Simulator**

#### For IoT Development:
- **Arduino IDE** or **PlatformIO**
- **Arduino Board** (Arduino Uno, Mega, or NodeMCU)
- **USB Cable** for board programming

### Installation

#### 1. Clone the Repository
```bash
git clone https://github.com/k12h005/HitAlert.git
cd HitAlert
```

#### 2. Install Flutter Dependencies
```bash
flutter pub get
```

#### 3. Resolve Android Dependencies
```bash
cd android
./gradlew clean
cd ..
```

#### 4. Get Flutter Packages
```bash
flutter pub upgrade
```

### Running the App

#### On Android Emulator
```bash
# List available devices
flutter devices

# Run on emulator
flutter run
```

#### On iOS Simulator
```bash
cd ios
pod install
cd ..
flutter run -d iPhone
```

#### On Connected Device
```bash
# For Android
flutter run -d <device_id>

# For iOS
flutter run -d <device_id>
```

#### Generate APK/AAB
```bash
# Debug APK
flutter build apk --debug

# Release APK
flutter build apk --release

# App Bundle (for Play Store)
flutter build appbundle --release
```

---

## 📁 Project Structure

```
HitAlert/
│
├── lib/
│   ├── main.dart                          # Application entry point
│   ├── common/
│   │   └── theme_helper.dart              # Theme & styling utilities
│   │
│   └── pages/
│       ├── splash_screen.dart             # App splash screen
│       ├── login_page.dart                # User login interface
│       ├── registration_page.dart         # User registration interface
│       ├── forgot_password_page.dart      # Password recovery
│       ├── forgot_password_verification_page.dart
│       ├── smoke.dart                     # Smoke detection page
│       │
│       └── widgets/
│           ├── dashboad.dart              # Main dashboard (sensor monitoring)
│           ├── header_widget.dart         # Header component
│           ├── setting.dart               # App settings & configuration
│           ├── emergency_confirmation_dialog.dart
│           ├── exit_confirmation_dialog.dart
│           ├── flame.dart                 # Flame detection display
│           ├── Temperature.dart           # Temperature monitoring
│           ├── MQ3.dart                   # Alcohol sensor display
│           ├── MQ4.dart                   # Gas sensor display
│           ├── FireStation_details.dart   # Fire station information
│           ├── Hospital_details.dart      # Hospital information
│           ├── About_us.dart              # About application
│           ├── FAQ.dart                   # Frequently asked questions
│           └── Terms.dart                 # Terms & conditions
│
├── android/                               # Android platform-specific code
│   ├── app/
│   │   └── src/
│   │       └── main/
│   │           ├── AndroidManifest.xml
│   │           ├── kotlin/                # Kotlin source files
│   │           └── res/                   # Android resources
│   └── build.gradle
│
├── ios/                                   # iOS platform-specific code
│   ├── Runner/                            # iOS app configuration
│   └── Runner.xcworkspace/
│
├── assets/
│   └── images/                            # App images & graphics
│       ├── logo.png
│       ├── bg_home.jpeg
│       ├── bg_image.jpeg
│       ├── splash.gif
│       ├── fire.png
│       ├── smoke.png
│       ├── high-temperature.png
│       ├── leakage.png
│       └── no-alcohol.png
│
├── test/
│   └── widget_test.dart                   # Widget tests
│
├── pubspec.yaml                           # Flutter dependencies
├── pubspec.lock                           # Locked dependency versions
├── analysis_options.yaml                  # Lint rules
└── README.md                              # This file
```

---

## 🔧 Core Modules

### 1. Authentication Module
**Files:** `login_page.dart`, `registration_page.dart`, `forgot_password_page.dart`

Handles user authentication with:
- Secure login/logout
- User registration with validation
- OTP-based password recovery
- Session management using SharedPreferences

### 2. Real-time Monitoring Dashboard
**File:** `dashboad.dart`

Displays real-time sensor data:
- **Flame Detection** - Fire hazard status
- **Smoke Detection** - Smoke levels
- **Temperature** - Current temperature readings
- **Alcohol Detection (MQ-3)** - Alcohol presence
- **Gas Levels (MQ-4)** - Hazardous gas detection
- **Emergency Alerts** - Alert history and status

### 3. Emergency Response System
**File:** `emergency_confirmation_dialog.dart`

Triggers emergency alerts:
- Confirms incident with user
- Sends SOS broadcast
- Notifies nearby hospitals and fire stations
- Provides real-time location
- Starts emergency timer

### 4. Location & Emergency Services
**Files:** `Hospital_details.dart`, `FireStation_details.dart`

Displays nearby emergency services:
- Hospital locations and contact info
- Fire station details
- Distance calculations
- Direct calling functionality
- GPS navigation integration

### 5. User Settings
**File:** `setting.dart`

Configurable options:
- Alert sensitivity thresholds
- Notification preferences
- Emergency contact management
- Dark/Light theme toggle
- Language preferences

---

## 🔌 IoT Hardware Integration

### Supported Sensors

#### 1. Flame Sensor
- **Detection Range:** Digital output (HIGH/LOW)
- **Response Time:** < 100ms
- **Use:** Detects open flame/fire

#### 2. Smoke Sensor (MQ Series)
- **Models:** MQ-2, MQ-5
- **Detects:** LPG, Smoke, Alcohol
- **Output:** Analog voltage 0-5V

#### 3. Temperature Sensor
- **Models:** DHT11, LM35
- **Range:** -40°C to 125°C
- **Accuracy:** ±2°C

#### 4. Alcohol Sensor (MQ-3)
- **Detection:** Alcohol vapor presence
- **Output:** Analog voltage 0-5V

#### 5. Gas Sensor (MQ-4)
- **Detection:** Methane, Natural gas
- **Output:** PPM measurement

---

## 🌐 API Integration

### Backend API Endpoints

```
Base URL: https://your-api-server.com/api

Authentication:
POST   /auth/login              - User login
POST   /auth/register           - User registration
POST   /auth/forgot-password    - Password recovery
POST   /auth/verify-otp         - OTP verification

Sensor Data:
POST   /sensors/data            - Upload sensor readings
GET    /sensors/latest          - Get latest sensor data

Alerts:
POST   /alerts/create           - Create new alert
GET    /alerts/active           - Get active alerts

Emergency Services:
GET    /emergency/hospitals     - List nearby hospitals
GET    /emergency/firestation   - List nearby fire stations
POST   /emergency/sos           - Trigger SOS broadcast
```

---

## 🤝 Contributing

We welcome contributions! To contribute:

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/amazing-feature`)
3. **Commit your changes** (`git commit -m 'Add amazing feature'`)
4. **Push to the branch** (`git push origin feature/amazing-feature`)
5. **Open a Pull Request**

---

## 📝 Dependencies

| Package | Version | Purpose |
|---------|---------|---------|
| flutter | SDK | Core framework |
| hexcolor | ^2.0.4 | Color management |
| http | ^0.13.3 | HTTP requests |
| font_awesome_flutter | ^9.1.0 | Icon library |
| otp_text_field | ^1.1.1 | OTP input field |
| animated_splash_screen | ^1.1.0 | Splash screen |
| shared_preferences | ^2.1.0 | Local storage |
| fluttertoast | 8.0.8 | Toast notifications |

---

## 🔒 Security & Privacy

- **Data Encryption:** Sensitive data is encrypted locally
- **HTTPS:** All API communication uses HTTPS
- **Authentication:** Token-based authentication with JWT
- **Privacy:** User location data only shared with emergency services

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 📞 Support

For issues and questions, please open an [Issue](https://github.com/k12h005/HitAlert/issues) on GitHub.

---

**Last Updated:** May 2026  
**Version:** 1.0.0  
**Status:** Active Development

---

*Built with ❤️ for emergency response and accident prevention*
