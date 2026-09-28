# PAWrtal

> A full-stack pet services marketplace connecting pet owners with veterinarians, groomers, and other pet care professionals — built with Flutter and deployed at [pawrtal.online](https://pawrtal.online).

---

## Overview

PAWrtal is a cross-platform mobile and web application that serves as a centralized hub for pet owners to discover, book, and interact with pet service providers. The platform bridges the gap between pet owners seeking quality care and professionals offering services, creating a seamless end-to-end experience for both sides of the marketplace.

---

## Features

- **Service Discovery** — Browse and search for nearby vets, groomers, and other pet professionals using integrated maps and geolocation
- **Appointment Scheduling** — Interactive calendar for booking and managing appointments with service providers
- **Real-Time Notifications** — Push notifications powered by Firebase Cloud Messaging to keep users updated on bookings and messages
- **Media Uploads** — Image and video support for pet profiles, service listings, and provider portfolios
- **QR Code Integration** — Generate and scan QR codes for quick profile sharing and check-ins
- **Authentication & OAuth** — Secure user authentication with OAuth 2.0 support via `flutter_web_auth_2`
- **Offline-Ready Storage** — Local data persistence using `get_storage` for a smooth offline experience
- **Responsive UI** — Adaptive layout across Android, iOS, and web platforms from a single codebase

---

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | Flutter (Dart) |
| Backend / Database | Appwrite v17 |
| Push Notifications | Firebase Cloud Messaging |
| Maps & Geolocation | flutter_map, geolocator, latlong2 |
| State Management | GetX |
| Local Storage | get_storage |
| Media Handling | image_picker, video_player, cached_network_image, file_picker |
| Calendar | table_calendar, jiffy |
| Networking | http, connectivity_plus |
| Auth | flutter_web_auth_2 |
| Deployment | Vercel (web), Firebase (Android) |

---

## Architecture

The project follows a feature-based structure under `lib/`, with state management handled by **GetX** for dependency injection, routing, and reactive state. The backend is powered entirely by **Appwrite**, handling authentication, database, storage, and real-time events. Firebase is used exclusively for push notification delivery via FCM.

```
PAWrtal/
├── lib/                  # Application source code
│   └── images/           # Local image assets
├── assets/images/        # Static assets
├── android/              # Android platform configuration
├── ios/                  # iOS platform configuration
├── web/                  # Web platform configuration
├── .github/workflows/    # CI/CD pipelines
├── pubspec.yaml          # Dependencies and project config
├── firebase.json         # Firebase project configuration
└── vercel.json           # Vercel deployment configuration
```

---

## Getting Started

### Prerequisites

- Flutter SDK `^3.5.2`
- Dart SDK `^3.5.2`
- An [Appwrite](https://appwrite.io) instance (self-hosted or cloud)
- A Firebase project with FCM enabled

### Installation

```bash
# Clone the repository
git clone https://github.com/mikey0-1/PAWrtal.git
cd PAWrtal

# Install dependencies
flutter pub get

# Run on web
flutter run -d chrome

# Run on Android/iOS
flutter run
```

### Environment Configuration

Configure your Appwrite endpoint and project credentials in `lib/` (see `firebase_options.dart` for Firebase setup). Ensure `google-services.json` is placed in `android/app/` for Android builds.

---

## Deployment

- **Web** — Deployed to [pawrtal.online](https://pawrtal.online) via **Vercel** using `vercel.json` configuration
- **Android** — Built and distributed via Firebase App Distribution
- **CI/CD** — Automated workflows defined in `.github/workflows/`

---

## License

This project is private and not intended for redistribution.
