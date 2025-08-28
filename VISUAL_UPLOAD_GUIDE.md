# 📱 Visual Upload Guide - Langkah demi Langkah

## 🌐 Step 1: Buat Repository GitHub

### **A. Buka GitHub**
```
1. Buka browser → ketik: github.com
2. Jika belum punya account:
   - Klik "Sign up"
   - Isi username, email, password
   - Verify email
3. Jika sudah punya account:
   - Klik "Sign in"
   - Login dengan username/password
```

### **B. Buat Repository Baru**
```
1. Setelah login, lihat pojok kanan atas
2. Klik tombol "+" (plus)
3. Pilih "New repository"

4. Isi form:
   Repository name: personalia
   Description: Aplikasi Android Personalia Sekolah
   
   ⚠️ PENTING:
   ✅ Pilih "Public" (bukan Private)
   ❌ JANGAN centang "Add a README file"
   ❌ JANGAN pilih ".gitignore template"
   ❌ JANGAN pilih "Choose a license"

5. Klik tombol hijau "Create repository"
```

## 📤 Step 2: Upload Files

### **A. Halaman Repository Kosong**
Setelah create repository, Anda akan melihat halaman seperti ini:
```
Quick setup — if you've done this kind of thing before
[HTTPS] [SSH] [GitHub CLI]

…or create a new repository on the command line
…or push an existing repository from the command line
…or import code from another repository

You can also upload an existing file or create a new file.
```

### **B. Klik Upload Link**
```
1. Cari teks: "upload an existing file"
2. Klik link tersebut
3. Anda akan masuk ke halaman upload
```

### **C. Prepare Files di Windows**
```
1. Buka Windows Explorer (File Manager)
2. Navigate ke: d:\personalia\personalia\
3. Anda akan melihat struktur seperti ini:

📁 d:\personalia\personalia\
├── 📁 .github\
├── 📁 app\
├── 📁 gradle\
├── 📄 .gitignore
├── 📄 build.gradle.kts
├── 📄 gradle.properties
├── 📄 gradlew
├── 📄 gradlew.bat
├── 📄 README.md
├── 📄 settings.gradle.kts
└── 📄 (file-file lainnya)
```

### **D. Select & Upload**
```
Metode 1 - Drag & Drop:
1. Di Windows Explorer, tekan Ctrl+A (select all)
2. Drag semua file/folder ke halaman GitHub upload
3. Tunggu sampai semua file ter-upload

Metode 2 - Choose Files:
1. Di halaman GitHub, klik "choose your files"
2. Di dialog yang muncul, tekan Ctrl+A
3. Klik "Open"
4. Tunggu upload selesai
```

## ✅ Step 3: Commit Changes

### **A. Isi Commit Message**
```
1. Scroll ke bawah halaman upload
2. Di bagian "Commit changes":
   
   Commit message: Initial commit - Personalia Android App
   
   Extended description (optional):
   Upload aplikasi Android Personalia untuk manajemen data sekolah
   
3. Pastikan "Commit directly to the main branch" dipilih
4. Klik tombol hijau "Commit changes"
```

### **B. Verify Upload**
```
Setelah commit, Anda akan kembali ke halaman repository.
Pastikan semua folder/file ter-upload:

✅ Folder .github (dengan subfolder workflows)
✅ Folder app (dengan subfolder src, dll)
✅ Folder gradle
✅ File build.gradle.kts
✅ File README.md
✅ File gradlew, gradlew.bat
✅ Dan file-file lainnya
```

## ⚙️ Step 4: Monitor Build Process

### **A. Akses GitHub Actions**
```
1. Di halaman repository, lihat tab di atas:
   [Code] [Issues] [Pull requests] [Actions] [Projects] [Wiki] [Security] [Insights] [Settings]

2. Klik tab "Actions"

3. Anda akan melihat workflow:
   "Build Android APK" dengan status:
   🟡 Yellow circle = Sedang running
   ✅ Green checkmark = Berhasil
   ❌ Red X = Gagal
```

### **B. Monitor Progress**
```
1. Klik pada workflow yang sedang running
2. Anda akan melihat jobs:
   - build (ubuntu-latest)
   
3. Klik "build" untuk melihat detail steps:
   - Checkout code ✅
   - Set up JDK 11 ✅
   - Cache Gradle packages ✅
   - Grant execute permission for gradlew ✅
   - Clean project ✅
   - Build debug APK 🟡 (sedang proses)
   - Upload APK artifact (pending)
   - Create Release (pending)

4. Tunggu sampai semua steps selesai (biasanya 5-10 menit)
```

## 📱 Step 5: Download APK

### **Metode A: Dari Releases (Recommended)**
```
1. Klik tab "Releases" di repository
2. Anda akan melihat release terbaru:
   "Personalia App v1.0.1" (atau nomor lain)
   
3. Di bagian "Assets", klik:
   📱 app-debug.apk (XX MB)
   
4. File akan terdownload ke folder Downloads
```

### **Metode B: Dari Actions Artifacts**
```
1. Di tab "Actions", klik workflow yang sudah selesai
2. Scroll ke bawah ke bagian "Artifacts"
3. Klik "personalia-debug-apk"
4. Download file ZIP
5. Extract ZIP, ambil file app-debug.apk
```

## 📲 Step 6: Install APK di Android

### **A. Transfer APK ke Android**
```
Metode 1 - USB Cable:
1. Connect Android ke PC via USB
2. Copy app-debug.apk ke folder Download di Android

Metode 2 - Cloud Storage:
1. Upload APK ke Google Drive/Dropbox
2. Download di Android

Metode 3 - Email:
1. Email APK ke diri sendiri
2. Download attachment di Android
```

### **B. Enable Unknown Sources**
```
1. Buka Settings di Android
2. Cari "Security" atau "Privacy"
3. Cari "Install unknown apps" atau "Unknown sources"
4. Pilih app yang akan digunakan install (File Manager/Chrome/dll)
5. Toggle ON "Allow from this source"
```

### **C. Install APK**
```
1. Buka File Manager di Android
2. Navigate ke folder tempat APK disimpan
3. Tap file "app-debug.apk"
4. Tap "Install"
5. Tunggu proses instalasi
6. Tap "Open" atau cari app "Personalia" di app drawer
```

## 🎉 Step 7: Test Aplikasi

### **A. First Launch**
```
1. Buka app "Personalia"
2. Anda akan melihat main screen dengan grid menu:
   - Staff categories (5 kotak)
   - Siswa classes (10 kotak)
```

### **B. Test Basic Functions**
```
1. Tap salah satu kategori staff (misal: "Guru")
2. Anda akan melihat daftar sample data
3. Tap tombol "+" untuk tambah data baru
4. Isi form dan tap save
5. Kembali ke list, data baru akan muncul
```

## 🚨 Troubleshooting

### **Upload Gagal**
```
Problem: "File too large" atau timeout
Solution:
- Upload folder satu per satu
- Pastikan koneksi internet stabil
- Hapus folder "build" jika ada (tidak perlu diupload)
```

### **Build Gagal**
```
Problem: Red X di GitHub Actions
Solution:
1. Klik workflow yang gagal
2. Lihat error message di logs
3. Biasanya masalah:
   - File gradlew tidak executable (sudah dihandle)
   - Missing files (re-upload)
```

### **APK Tidak Bisa Install**
```
Problem: "App not installed"
Solution:
- Pastikan Android version 5.1+
- Enable "Unknown sources"
- Download ulang APK (mungkin corrupt)
```

---

## 📞 Butuh Bantuan Lebih?

Jika ada langkah yang tidak jelas atau error:

1. **Screenshot** halaman yang bermasalah
2. **Copy-paste** error message (jika ada)
3. **Sebutkan** di langkah mana Anda stuck

Saya akan bantu troubleshoot masalah spesifik Anda! 🚀
