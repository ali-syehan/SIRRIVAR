# AliVAR WebView Native Android

Project Android native sederhana untuk menjalankan website HTML/CSS/JS lokal melalui Android WebView.

## Struktur Project

```text
AliVAR_WebView_Native_FIXED/
├── .github/workflows/build-apk.yml
├── app/src/main/assets/index.html
├── app/src/main/java/com/alisyehan/varwebview/MainActivity.java
├── app/src/main/AndroidManifest.xml
├── app/build.gradle
├── build.gradle
├── settings.gradle
├── gradle.properties
├── GITHUB_WORKFLOW_build-apk.yml
└── README.md
```

## Versi Build

- Android Gradle Plugin: 8.5.2
- Gradle: 8.7
- JDK: 17
- compileSdk: 34
- targetSdk: 34
- minSdk: 23
- Bahasa native: Java
- AndroidX: tidak dipakai

## Cara Menjalankan di Android Studio

1. Extract ZIP.
2. Buka Android Studio.
3. Pilih **Open**.
4. Pilih folder project `AliVAR_WebView_Native_FIXED`.
5. Tunggu Gradle sync selesai.
6. Klik **Run** untuk menjalankan di emulator atau HP Android.

## Cara Upload ke GitHub

```bash
cd AliVAR_WebView_Native_FIXED
git init
git branch -M main
git add .
git commit -m "Initial Android WebView project"
git remote add origin https://github.com/USERNAME/NAMA-REPO.git
git push -u origin main
```

Ganti `USERNAME` dan `NAMA-REPO` sesuai repository Anda.

## Cara Build APK dari GitHub Actions

1. Buka repository GitHub.
2. Buka tab **Actions**.
3. Pilih workflow **Build Android APK**.
4. Klik **Run workflow**.
5. Pilih branch `main`.
6. Klik **Run workflow**.

Workflow juga otomatis berjalan setiap kali ada push ke branch `main`.

## Lokasi APK Hasil Build

Jika build dilakukan di GitHub Actions, APK akan tersedia sebagai artifact bernama:

```text
android-debug-apk
```

File APK berada di:

```text
app/build/outputs/apk/debug/app-debug.apk
```

## Cara Download Artifact APK

1. Buka tab **Actions**.
2. Klik run workflow yang berhasil.
3. Scroll ke bagian **Artifacts**.
4. Download `android-debug-apk`.

## Jika Tab Actions Tidak Muncul

- Pastikan repository bukan empty repository.
- Pastikan file workflow ada di `.github/workflows/build-apk.yml`.
- Pastikan file sudah di-commit dan di-push ke branch `main`.
- Coba refresh halaman GitHub.

## Jika Folder .github Tidak Terlihat

Folder `.github` adalah hidden folder. Di GitHub web biasanya tetap terlihat setelah diupload. Di komputer lokal, aktifkan tampilan hidden files.

Sebagai cadangan, workflow juga disalin di root project dengan nama:

```text
GITHUB_WORKFLOW_build-apk.yml
```

Tetapi file yang dipakai GitHub Actions tetap:

```text
.github/workflows/build-apk.yml
```
