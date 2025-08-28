# 📤 Panduan Upload ke GitHub - Step by Step

## 🌐 Metode 1: Upload via Web Browser (Termudah)

### **Step 1: Buat Repository**
1. Buka https://github.com
2. Login/Sign up
3. Klik tombol "+" → "New repository"
4. Isi form:
   - Repository name: `personalia`
   - Description: `Aplikasi Android Personalia Sekolah`
   - ✅ Public (agar GitHub Actions gratis)
   - ❌ JANGAN centang "Add a README file" (kita punya sendiri)
   - ❌ JANGAN pilih .gitignore (kita punya sendiri)
5. Klik "Create repository"

### **Step 2: Upload Files**
Setelah repository dibuat, Anda akan melihat halaman kosong dengan instruksi.

#### **A. Upload via Drag & Drop**
1. Klik link **"uploading an existing file"**
2. **Buka Windows Explorer** ke folder `d:\personalia\personalia\`
3. **Select All** (Ctrl+A) semua file dan folder
4. **Drag & Drop** ke area upload GitHub

#### **B. Upload via Choose Files**
1. Klik **"choose your files"**
2. Navigate ke `d:\personalia\personalia\`
3. Select semua file (Ctrl+A)
4. Klik "Open"

### **Step 3: Commit Changes**
1. Scroll ke bawah
2. Isi commit message: `Initial commit - Personalia Android App`
3. Klik **"Commit changes"**

### **Step 4: Tunggu Build**
1. Klik tab **"Actions"**
2. Tunggu workflow "Build Android APK" selesai (5-10 menit)
3. Jika berhasil, akan ada ✅ green checkmark

### **Step 5: Download APK**
1. Klik tab **"Releases"**
2. Download file `app-debug.apk`

---

## 💻 Metode 2: Upload via GitHub Desktop (User-Friendly)

### **Step 1: Install GitHub Desktop**
1. Download dari https://desktop.github.com/
2. Install dan login dengan akun GitHub

### **Step 2: Clone Repository**
1. Di GitHub web, klik tombol hijau **"Code"**
2. Klik **"Open with GitHub Desktop"**
3. Pilih folder untuk clone (misal: `C:\Projects\`)

### **Step 3: Copy Files**
1. Buka Windows Explorer ke folder yang di-clone
2. Copy semua file dari `d:\personalia\personalia\` ke folder clone
3. GitHub Desktop akan otomatis detect changes

### **Step 4: Commit & Push**
1. Di GitHub Desktop, isi commit message
2. Klik **"Commit to main"**
3. Klik **"Push origin"**

---

## ⌨️ Metode 3: Upload via Command Line (Advanced)

### **Step 1: Install Git**
1. Download dari https://git-scm.com/
2. Install dengan default settings

### **Step 2: Setup Git**
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### **Step 3: Upload**
```bash
# Masuk ke folder project
cd d:\personalia\personalia

# Initialize git
git init

# Add remote repository (ganti YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/personalia.git

# Add all files
git add .

# Commit
git commit -m "Initial commit - Personalia Android App"

# Push to GitHub
git branch -M main
git push -u origin main
```

---

## 📋 Checklist Files yang Harus Diupload

Pastikan struktur folder seperti ini setelah upload:

```
📁 personalia/
├── 📁 .github/
│   ├── 📁 workflows/
│   │   └── 📄 build-apk.yml
│   └── 📁 ISSUE_TEMPLATE/
│       ├── 📄 bug_report.md
│       └── 📄 feature_request.md
├── 📁 app/
│   ├── 📁 build.gradle.kts
│   ├── 📁 src/
│   │   └── 📁 main/
│   │       ├── 📁 java/
│   │       ├── 📁 res/
│   │       └── 📄 AndroidManifest.xml
│   └── 📄 proguard-rules.pro
├── 📁 gradle/
│   ├── 📁 libs.versions.toml
│   └── 📁 wrapper/
├── 📄 .gitignore
├── 📄 build.gradle.kts
├── 📄 gradle.properties
├── 📄 gradlew
├── 📄 gradlew.bat
├── 📄 local.properties (optional)
├── 📄 README.md
├── 📄 settings.gradle.kts
├── 📄 GITHUB_SETUP.md
├── 📄 BUILD_INSTRUCTIONS.md
└── 📄 TEST_SIMULATION.md
```

---

## 🚨 Troubleshooting Upload

### **Problem: File terlalu besar**
**Solution:**
- GitHub limit 100MB per file
- Jika ada file besar, exclude dari upload
- File yang biasanya besar: `local.properties`, folder `build/`

### **Problem: Upload gagal/timeout**
**Solution:**
- Upload dalam batch kecil
- Upload folder satu per satu
- Gunakan koneksi internet yang stabil

### **Problem: Structure folder rusak**
**Solution:**
- Pastikan upload dengan struktur folder utuh
- Jangan upload file satu-satu, tapi upload folder lengkap

### **Problem: GitHub Actions tidak jalan**
**Solution:**
- Pastikan file `.github/workflows/build-apk.yml` ter-upload
- Repository harus Public untuk GitHub Actions gratis
- Tunggu beberapa menit setelah upload

---

## 🎯 Tips Upload Sukses

### **✅ Do's:**
- Upload semua file sekaligus (maintain structure)
- Gunakan commit message yang jelas
- Set repository sebagai Public
- Pastikan file `.github/workflows/build-apk.yml` ter-upload

### **❌ Don'ts:**
- Jangan upload file `local.properties` (contains sensitive info)
- Jangan upload folder `build/` (akan di-generate otomatis)
- Jangan upload satu file per satu (struktur bisa rusak)
- Jangan set repository Private (GitHub Actions tidak gratis)

---

## 🔄 Setelah Upload Berhasil

### **1. Verify Upload**
- Cek semua folder dan file ter-upload dengan benar
- Pastikan struktur sama dengan local

### **2. Monitor Build**
- Klik tab "Actions"
- Tunggu workflow selesai
- Jika ada error, cek logs untuk troubleshooting

### **3. Download APK**
- Setelah build sukses, klik tab "Releases"
- Download `app-debug.apk`
- Install di Android device

### **4. Test App**
- Install APK di Android
- Test semua fitur utama
- Report bug jika ada masalah

---

## 📞 Butuh Bantuan?

Jika masih kesulitan:

1. **Screenshot error** yang muncul
2. **Describe step** yang bermasalah
3. **Share repository URL** (jika sudah dibuat)

Saya akan bantu troubleshoot masalah spesifik Anda!
