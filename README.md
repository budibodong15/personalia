# 📱 Personalia Sekolah

Aplikasi Android modern untuk mengelola data personil sekolah (Staff dan Siswa) dengan teknologi terkini.

## 🎯 Fitur Utama

### 👥 **Manajemen Staff**
- ✅ 5 Kategori: Staff, Guru, Guru Extrakulikuler, Tata Usaha & Perpustakaan, Karyawan Rumah Tangga
- ✅ Data lengkap: Nama, Tempat/Tanggal Lahir, Jabatan, Alamat, No HP, Foto
- ✅ CRUD operations (Create, Read, Update, Delete)
- ✅ Search & filter real-time

### 🎓 **Manajemen Siswa**
- ✅ 10 Kelas: KPP A/B/C, X-1/X-2, XI-1/XI-2, XII-1/XII-2, KPA
- ✅ Data lengkap: Nama, NIS, NISN, Tempat/Tanggal Lahir, Paroki, Sekolah Asal, Alamat, No HP Ortu
- ✅ CRUD operations lengkap
- ✅ Search & filter per kelas

### 🔧 **Teknologi**
- ✅ **Kotlin** + **Jetpack Compose** (UI Modern)
- ✅ **Material Design 3** (Consistent UI/UX)
- ✅ **JSON Storage** (No database required)
- ✅ **MVVM Architecture** (Clean & Scalable)
- ✅ **StateFlow** (Reactive UI)

## 📥 Download & Install

### **Metode 1: Download APK Langsung**
1. **[📱 Download APK Terbaru](../../releases/latest/download/app-debug.apk)**
2. Enable "Install from Unknown Sources" di Android Settings
3. Install APK yang sudah didownload
4. Buka aplikasi "Personalia"

### **Metode 2: Build Sendiri**
```bash
# Clone repository
git clone https://github.com/your-username/personalia.git
cd personalia

# Build APK
./gradlew assembleDebug

# APK tersimpan di: app/build/outputs/apk/debug/app-debug.apk
```

## 🚀 Cara Menggunakan

### **1. Halaman Utama**
- Pilih kategori Staff atau kelas Siswa
- Grid layout dengan ikon yang jelas

### **2. Melihat Data**
- Tap kategori untuk melihat daftar
- Search menggunakan ikon 🔍
- Data ditampilkan dalam card yang rapi

### **3. Menambah Data**
- Tap tombol ➕ (FAB) di list screen
- Isi form dengan data lengkap
- Tap 💾 untuk menyimpan

### **4. Mencari Data**
- Tap ikon 🔍 di top bar
- Ketik nama, jabatan, atau info lain
- Filter real-time saat mengetik

## 📊 Screenshots

| Main Screen | Staff List | Add Staff | Search |
|-------------|------------|-----------|---------|
| ![Main](screenshots/main.png) | ![List](screenshots/list.png) | ![Add](screenshots/add.png) | ![Search](screenshots/search.png) |

## 🔧 Requirements

- **Android 5.1+** (API Level 22+)
- **50MB** storage space
- **RAM 2GB+** (recommended)

## 🏗️ Architecture

```
📁 app/src/main/java/com/example/personalia/
├── 📁 model/          # Data models (Staff, Siswa)
├── 📁 repository/     # Data management (JSON storage)
├── 📁 viewmodel/      # Business logic (MVVM)
├── 📁 ui/
│   ├── 📁 screens/    # UI screens (Compose)
│   ├── 📁 components/ # Reusable UI components
│   └── 📁 theme/      # Material Design theme
├── 📁 navigation/     # Navigation logic
└── 📁 utils/          # Utilities (Photo, Export)
```

## 📈 Data Storage

- **Format**: JSON files di internal storage
- **Location**: `/data/data/com.example.personalia/files/`
- **Files**: 
  - `staff_data.json` - Data semua staff
  - `siswa_data.json` - Data semua siswa
- **Backup**: Export/import functionality

## 🔒 Privacy & Security

- ✅ **Data lokal** - Tidak ada server external
- ✅ **Internal storage** - Data private per app
- ✅ **No permissions** - Tidak perlu akses khusus
- ✅ **Offline first** - Bekerja tanpa internet

## 🐛 Known Issues & Roadmap

### **Current Limitations**
- 📸 Photo management belum fully implemented
- 📤 Export/import belum ada UI
- 📋 Detail view belum ada

### **Roadmap v2.0**
- [ ] Photo upload & management
- [ ] Export to PDF/Excel
- [ ] Data import from CSV
- [ ] Backup & restore
- [ ] Print functionality
- [ ] Advanced search filters

## 🤝 Contributing

1. Fork repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open Pull Request

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

## 📞 Support

- 🐛 **Bug Reports**: [Create Issue](../../issues/new?template=bug_report.md)
- 💡 **Feature Requests**: [Create Issue](../../issues/new?template=feature_request.md)
- 📧 **Email**: your-email@example.com

## 🙏 Acknowledgments

- [Jetpack Compose](https://developer.android.com/jetpack/compose) - Modern UI toolkit
- [Material Design 3](https://m3.material.io/) - Design system
- [Gson](https://github.com/google/gson) - JSON parsing
- [Coil](https://coil-kt.github.io/coil/) - Image loading

---

⭐ **Star this repo** if you find it helpful!

![Build Status](../../actions/workflows/build-apk.yml/badge.svg)
![GitHub release](https://img.shields.io/github/v/release/your-username/personalia)
![GitHub downloads](https://img.shields.io/github/downloads/your-username/personalia/total)
