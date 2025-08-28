# 🚀 Panduan Setup GitHub & Download APK

## 📋 Langkah-langkah Lengkap

### **1. Buat GitHub Repository**

#### **A. Buat Account GitHub (jika belum punya)**
1. Kunjungi [github.com](https://github.com)
2. Klik "Sign up" 
3. Isi username, email, password
4. Verify email

#### **B. Buat Repository Baru**
1. Login ke GitHub
2. Klik tombol **"+"** di pojok kanan atas
3. Pilih **"New repository"**
4. Isi detail:
   - **Repository name**: `personalia`
   - **Description**: `Aplikasi Android Personalia Sekolah`
   - **Visibility**: Public (agar GitHub Actions gratis)
   - ✅ **Add README file**
   - ✅ **Add .gitignore** → pilih "Android"
   - **License**: MIT License (optional)
5. Klik **"Create repository"**

### **2. Upload Kode ke GitHub**

#### **Metode A: Via GitHub Web Interface (Mudah)**
1. Di repository yang baru dibuat, klik **"uploading an existing file"**
2. **Drag & drop** atau **choose files** semua folder/file dari `d:\personalia\personalia\`
3. **PENTING**: Upload struktur folder seperti ini:
   ```
   📁 app/
   📁 gradle/
   📁 .github/workflows/
   📄 build.gradle.kts
   📄 settings.gradle.kts
   📄 gradlew
   📄 gradlew.bat
   📄 gradle.properties
   📄 README.md
   ```
4. Scroll ke bawah, isi commit message: `Initial commit - Personalia App`
5. Klik **"Commit changes"**

#### **Metode B: Via Git Command Line**
```bash
# Di folder d:\personalia\personalia\
git init
git add .
git commit -m "Initial commit - Personalia App"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/personalia.git
git push -u origin main
```

### **3. Tunggu Auto-Build APK**

#### **A. Cek GitHub Actions**
1. Di repository GitHub, klik tab **"Actions"**
2. Anda akan melihat workflow **"Build Android APK"** sedang running
3. Klik workflow untuk melihat progress
4. Tunggu sampai selesai (biasanya 5-10 menit)

#### **B. Status Build**
- 🟡 **Yellow dot**: Sedang building
- ✅ **Green checkmark**: Build berhasil
- ❌ **Red X**: Build gagal (perlu troubleshooting)

### **4. Download APK**

#### **Metode A: Dari Artifacts (Langsung setelah build)**
1. Di halaman Actions, klik workflow yang sudah selesai
2. Scroll ke bawah ke bagian **"Artifacts"**
3. Klik **"personalia-debug-apk"** untuk download
4. Extract file ZIP, ambil `app-debug.apk`

#### **Metode B: Dari Releases (Otomatis dibuat)**
1. Di repository, klik tab **"Releases"**
2. Klik release terbaru (misal: `v1.0.1`)
3. Di bagian **"Assets"**, klik **"app-debug.apk"**
4. File APK akan terdownload langsung

### **5. Install APK di Android**

#### **A. Persiapan Android**
1. Buka **Settings** → **Security** (atau **Privacy**)
2. Cari **"Install unknown apps"** atau **"Unknown sources"**
3. Pilih browser/file manager yang akan digunakan
4. **Enable** "Allow from this source"

#### **B. Install APK**
1. Transfer file `app-debug.apk` ke Android (via USB, email, cloud, dll)
2. Buka **File Manager** di Android
3. Navigate ke folder tempat APK disimpan
4. Tap file **"app-debug.apk"**
5. Tap **"Install"**
6. Tunggu proses instalasi selesai
7. Tap **"Open"** atau cari app **"Personalia"** di app drawer

## 🔧 Troubleshooting

### **Build Gagal di GitHub Actions**

#### **Error: Gradle build failed**
```yaml
# Solusi: Pastikan file gradlew executable
# Tambahkan di workflow sebelum build:
- name: Grant execute permission for gradlew
  run: chmod +x gradlew
```

#### **Error: Java version mismatch**
```yaml
# Solusi: Pastikan Java version konsisten
- name: Set up JDK 11
  uses: actions/setup-java@v4
  with:
    java-version: '11'
    distribution: 'temurin'
```

#### **Error: Android SDK not found**
```yaml
# Solusi: GitHub Actions sudah include Android SDK
# Pastikan build.gradle.kts menggunakan compileSdk yang tersedia
android {
    compileSdk 34  # Gunakan yang stabil
}
```

### **APK Tidak Bisa Install**

#### **Error: "App not installed"**
- **Penyebab**: APK corrupt atau tidak compatible
- **Solusi**: Download ulang APK, pastikan Android version compatible

#### **Error: "Unknown sources blocked"**
- **Penyebab**: Security setting belum diaktifkan
- **Solusi**: Enable "Install unknown apps" untuk browser/file manager

#### **Error: "Parse error"**
- **Penyebab**: APK file rusak saat download/transfer
- **Solusi**: Download ulang, pastikan transfer complete

### **App Crash saat Launch**

#### **Cek Logcat**
```bash
# Connect Android via USB, enable USB debugging
adb logcat | grep "com.example.personalia"
```

#### **Common Issues**
- **Missing permissions**: Sudah dihandle di AndroidManifest
- **Storage access**: Menggunakan internal storage (no permission needed)
- **Memory issues**: Restart device, close other apps

## 📱 Testing Checklist

Setelah install, test fitur-fitur ini:

### **✅ Basic Functionality**
- [ ] App launches without crash
- [ ] Main screen displays grid menu
- [ ] Navigation to staff/siswa lists works
- [ ] Sample data loads correctly

### **✅ Staff Management**
- [ ] View staff by category
- [ ] Add new staff works
- [ ] Form validation works
- [ ] Search functionality works
- [ ] Data persists after app restart

### **✅ Siswa Management**
- [ ] View siswa by class
- [ ] Add new siswa works
- [ ] NIS/NISN validation works
- [ ] Search functionality works
- [ ] Data persists after app restart

### **✅ UI/UX**
- [ ] Material Design 3 theme applied
- [ ] Smooth animations
- [ ] Responsive layout
- [ ] No UI glitches

## 🎯 Next Steps

Setelah APK berhasil diinstall dan ditest:

1. **📝 Feedback**: Laporkan bug atau request fitur
2. **⭐ Star Repository**: Jika aplikasi berguna
3. **🔄 Updates**: Watch repository untuk update terbaru
4. **📤 Share**: Bagikan ke kolega yang membutuhkan

## 📞 Support

Jika ada masalah:

1. **🐛 Bug Report**: Create issue di GitHub
2. **💬 Discussion**: Gunakan GitHub Discussions
3. **📧 Direct Contact**: Email developer

---

**🎉 Selamat! Anda sekarang memiliki aplikasi Personalia yang bisa digunakan!**
