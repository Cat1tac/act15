# Inventory Management App

A Flutter inventory management application backed by Cloud Firestore with real-time updates.

## Features

- **Full CRUD** — Create, read, update, and delete inventory items stored in Firestore.
- **Real-time sync** — Uses `StreamBuilder` so the list updates instantly when data changes in Firestore.
- **Form validation** — All fields are validated (non-empty, numeric checks, no negative values).
- **Clean architecture** — Firestore logic lives in a dedicated `FirestoreService`; widgets handle display only.

## Enhanced Features

### 1. Search / Filter
A search bar in the app bar lets users filter the inventory list in real time by name or description. Filtering is performed client-side on the streamed data so results update instantly as the user types.

### 2. Low-Stock Warning Indicator
Items with a quantity of 5 or fewer display a warning icon and red quantity text, making it easy to spot items that need restocking at a glance.

## Project Structure

```
lib/
├── main.dart                  # App entry, Firebase init
├── firebase_options.dart      # FlutterFire config (generated)
├── models/
│   └── item.dart              # Item data model
├── screens/
│   ├── home_screen.dart       # List view with StreamBuilder
│   └── item_form_screen.dart  # Add/Edit form with validation
└── services/
    └── firestore_service.dart # Firestore CRUD operations
```

## Getting Started

1. Clone this repo.
2. Run `flutterfire configure` to connect your own Firebase project.
3. Enable Firestore in test mode from the Firebase console.
4. Run `flutter pub get` then `flutter run`.

## Reflection

See `reflection.md` in the repo root.
