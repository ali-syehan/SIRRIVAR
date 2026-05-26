# Ali VAR WebView Android Native

Project ini adalah Android native WebView sederhana untuk menjalankan website lokal dari folder assets.

## Versi build yang dipakai

- Android Gradle Plugin: 8.5.2
- Gradle: 8.7, disiapkan lewat GitHub Actions
- JDK: 17
- compileSdk: 34
- targetSdk: 34
- minSdk: 23
- Bahasa MainActivity: Java native
- AndroidX: tidak dipakai

Kombinasi ini dipilih agar stabil, sederhana, dan kompatibel untuk Android Studio maupun GitHub Actions.

## Struktur project

```text
AliVAR_WebView_Native/
├── .github/
│   └── workflows/
│       └── build-apk.yml
├── app/
│   ├── build.gradle
│   └── src/main/
│       ├── AndroidManifest.xml
│       ├── assets/
│       │   └── index.html
│       ├── java/com/alisyehan/varwebview/
│       │   └── MainActivity.java
│       └── res/values/
│           └── styles.xml
├── build.gradle
├── gradle.properties
├── settings.gradle
├── GITHUB_WORKFLOW_build-apk.yml
├── .gitignore
└── README.md
```

## Lokasi file website

File website ada di:

```text
app/src/main/assets/index.html
```

WebView membuka file ini:

```text
file:///android_asset/index.html
```

Kalau nanti ada file tambahan seperti `style.css`, `app.js`, gambar, atau font, masukkan ke folder:

```text
app/src/main/assets/
```

Lalu panggil dari `index.html` memakai path relatif, misalnya:

```html
<link rel="stylesheet" href="style.css">
<script src="app.js"></script>
<img src="images/logo.png">
```

## Cara menjalankan di Android Studio

1. Extract ZIP project ini.
2. Buka Android Studio.
3. Pilih **Open**.
4. Pilih folder project `AliVAR_WebView_Native`.
5. Tunggu Gradle sync selesai.
6. Klik **Run** untuk menjalankan di emulator atau HP Android.

## Cara upload ke GitHub

Buat repository baru di GitHub. Pastikan branch utama bernama `main`.

Lewat terminal:

```bash
cd AliVAR_WebView_Native
git init
git branch -M main
git add .
git commit -m "Initial Android WebView project"
git remote add origin https://github.com/USERNAME/NAMA-REPO.git
git push -u origin main
```

Ganti `USERNAME` dan `NAMA-REPO` sesuai repo Anda.

## Cara menjalankan GitHub Actions

Workflow asli ada di:

```text
.github/workflows/build-apk.yml
```

Salinannya juga disediakan di root:

```text
GITHUB_WORKFLOW_build-apk.yml
```

Workflow akan otomatis berjalan saat push ke branch `main`.

Untuk menjalankan manual:

1. Buka repository GitHub.
2. Buka tab **Actions**.
3. Pilih **Build Android APK**.
4. Klik **Run workflow**.
5. Pilih branch `main`.
6. Klik tombol **Run workflow**.

## Lokasi APK hasil build

Jika build berhasil, APK debug ada di:

```text
app/build/outputs/apk/debug/app-debug.apk
```

Di GitHub Actions, APK akan diupload sebagai artifact bernama:

```text
android-debug-apk
```

## Cara download artifact APK

1. Buka tab **Actions** di GitHub.
2. Klik workflow run yang berhasil.
3. Scroll ke bagian **Artifacts**.
4. Download artifact bernama `android-debug-apk`.
5. Extract file ZIP artifact tersebut.
6. Di dalamnya ada `app-debug.apk`.

## Jika tab Actions tidak muncul

Coba cek ini:

1. Pastikan file workflow benar-benar ada di `.github/workflows/build-apk.yml`.
2. Pastikan repo sudah di-push ke GitHub, bukan hanya ada di komputer lokal.
3. Pastikan branch yang dipakai adalah `main`.
4. Refresh halaman GitHub.
5. Buka URL repo, lalu tambahkan `/actions` di belakangnya.
6. Cek Settings > Actions > General, pastikan GitHub Actions tidak dimatikan.

## Jika folder .github tidak terlihat

Folder `.github` adalah hidden folder karena diawali titik.

Solusi:

- Di macOS Finder: tekan `Command + Shift + .`
- Di Windows File Explorer: aktifkan **View > Hidden items**
- Di VS Code: folder `.github` biasanya langsung terlihat
- Di terminal: gunakan `ls -la`

Karena folder `.github` kadang tidak terlihat, file workflow juga disalin ke root project sebagai:

```text
GITHUB_WORKFLOW_build-apk.yml
```

Namun GitHub Actions hanya membaca workflow dari lokasi asli:

```text
.github/workflows/build-apk.yml
```
