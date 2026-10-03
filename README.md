TalkReady — Mobile Setup Guide

TalkReady is an AI-powered English proficiency and communication training app built for aspiring call center professionals. It combines a cross-platform Flutter client with a Firebase backend and external machine learning/speech APIs to help users practice and improve their spoken English.

Note: This mobile client is currently built and tested for the Android platform only.

Prerequisites
Make sure the following are installed and available on your system PATH:

Tool	Purpose
Git	Clone and manage the repository
Flutter SDK (Stable channel)	Build and run the mobile client
Node.js & npm (LTS)	Install and run Firebase Functions
Java Development Kit (JDK)	Required for Android Gradle builds and emulators
Firebase CLI	Deploy and manage Firebase services
Install the Firebase CLI globally: npm install -g firebase-tools

TalkReady/
├── talkready_mobile/   # Flutter/Dart client (core app logic)
├── functions/          # Firebase Cloud Functions (speech + AI processing)
├── firebase.json       # Deployment config + emulator port mappings
└── .vscode/            # Shared VS Code settings

git clone https://github.com/aisamae13/TalkReady.git
cd TalkReady

cd functions
npm install
cd ..
firebase login
firebase use your-firebase-project-id

cd talkready_mobile
flutter pub get

flutter devices
flutter run

⚙️ Configuration Notes
Hardware acceleration: In talkready_mobile/android/app/src/main/AndroidManifest.xml, make sure the <application> tag has android:hardwareAccelerated="true" — this keeps in-app WebViews running smoothly.
Firestore security rules: Review and adjust the rules referenced in firebase.json before deploying to production.
