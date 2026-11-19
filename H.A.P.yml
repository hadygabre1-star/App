name: Build Android APK

on:
  push:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v4

      - name: Set up JDK 17
        uses: actions/setup-java@v4
        with:
          distribution: 'temurin'
          java-version: '17'

      - name: Build with Android Sign/Build Action
        uses: reactivecircus/android-emulator-runner@v2
        with:
          api-level: 29
          target: google_apis
          arch: x86_64
          profile: Nexus 6
          script: ./gradlew assembleDebug || ./app/gradlew assembleDebug || gradle assembleDebug
