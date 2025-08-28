# 📱 Simulasi Testing Aplikasi Personalia

## 🎯 Skenario Testing yang Bisa Dilakukan

### **1. Launch App & Main Screen**
```
✅ App Launch
- Splash screen (jika ada)
- Main screen dengan grid menu:
  * Staff categories (5 kategori)
  * Siswa classes (10 kelas)
- Material Design 3 theme
```

### **2. Testing Staff Management**

#### **A. View Staff List**
```
Navigation: Main → "Guru" category
Expected Result:
✅ StaffListScreen terbuka
✅ Title: "Daftar Guru" 
✅ Sample data muncul:
   - John Doe (Guru Matematika)
   - Ahmad (Guru Ekstrakurikuler Musik)
✅ Search icon di top bar
✅ FAB "+" untuk tambah data
```

#### **B. Search Staff**
```
Action: Tap search icon → ketik "john"
Expected Result:
✅ Search field muncul
✅ Filter real-time
✅ Hanya John Doe yang muncul
✅ Tap search lagi untuk close
```

#### **C. Add New Staff**
```
Action: Tap FAB "+"
Expected Result:
✅ StaffEntryScreen terbuka
✅ Title: "Tambah Guru Baru"
✅ Form fields:
   - Foto (placeholder)
   - Nama Lengkap *
   - Tempat Lahir
   - Tanggal Lahir
   - Jabatan *
   - Alamat
   - No HP
✅ Save FAB di bottom right
```

#### **D. Fill & Save Staff**
```
Action: 
- Isi Nama: "Budi Santoso"
- Isi Jabatan: "Guru Bahasa Indonesia"
- Isi data lainnya
- Tap Save FAB

Expected Result:
✅ Loading indicator muncul
✅ "Staff berhasil ditambahkan" message
✅ Navigate back ke list
✅ Data baru muncul di list
✅ Data tersimpan (persistent)
```

### **3. Testing Siswa Management**

#### **A. View Siswa List**
```
Navigation: Main → "X-1" class
Expected Result:
✅ SiswaListScreen terbuka
✅ Title: "Daftar Siswa Kelas X-1"
✅ Sample data:
   - Budi Santoso (NIS: 2021001)
   - Ani Wijaya (NIS: 2021002)
✅ Detail info: NIS, NISN, Tempat lahir, dll
```

#### **B. Add New Siswa**
```
Action: Tap FAB "+"
Expected Result:
✅ SiswaEntryScreen terbuka
✅ Title: "Tambah Siswa Kelas X-1"
✅ Form fields:
   - Foto
   - Nama Lengkap *
   - NIS * (min 5 char)
   - NISN * (min 10 char)
   - Tempat Lahir
   - Tanggal Lahir
   - Paroki
   - Sekolah Asal
   - Alamat
   - No HP Orang Tua
```

#### **C. Form Validation**
```
Action: Tap Save tanpa isi data
Expected Result:
✅ Error messages muncul:
   - "Nama tidak boleh kosong"
   - "NIS tidak boleh kosong"
   - "NISN tidak boleh kosong"
✅ Fields dengan error highlighted merah
✅ Save button tetap enabled untuk retry
```

### **4. Testing Data Persistence**

#### **A. Add Data & Restart App**
```
Action:
1. Tambah staff baru
2. Close app completely
3. Reopen app
4. Navigate ke staff list

Expected Result:
✅ Data yang ditambah masih ada
✅ Sample data + data baru semua muncul
✅ JSON file tersimpan di internal storage
```

#### **B. Multiple Categories**
```
Action:
1. Tambah staff di kategori "Guru"
2. Tambah staff di kategori "Tata Usaha"
3. View masing-masing kategori

Expected Result:
✅ Data tersimpan per kategori
✅ Filter kategori bekerja
✅ Data tidak tercampur antar kategori
```

### **5. Testing Edge Cases**

#### **A. Empty Categories**
```
Action: Tap kategori yang belum ada data (misal: "Staff")
Expected Result:
✅ List screen terbuka
✅ Empty state message
✅ FAB tetap ada untuk tambah data
```

#### **B. Long Text Input**
```
Action: Isi alamat dengan text sangat panjang
Expected Result:
✅ Text field expand (multiline)
✅ Data tersimpan lengkap
✅ Display di list terpotong dengan ellipsis
```

#### **C. Special Characters**
```
Action: Isi nama dengan karakter khusus (é, ñ, etc)
Expected Result:
✅ Input diterima
✅ Display benar di list
✅ Search berfungsi dengan karakter khusus
```

### **6. Testing Performance**

#### **A. Large Data Set**
```
Action: Tambah 50+ staff/siswa
Expected Result:
✅ List scroll smooth
✅ Search tetap responsive
✅ App tidak crash
✅ Memory usage reasonable
```

#### **B. Rapid Navigation**
```
Action: Navigate cepat antar screens
Expected Result:
✅ No lag atau freeze
✅ Data loading consistent
✅ Back navigation bekerja
```

## 🐛 Potential Issues & Solutions

### **Issue 1: App Crash on Launch**
```
Possible Cause: Missing dependencies
Solution: Check build.gradle sync
```

### **Issue 2: Data Not Saving**
```
Possible Cause: Storage permission
Solution: Check internal storage access
```

### **Issue 3: Search Not Working**
```
Possible Cause: State management issue
Solution: Check StateFlow updates
```

### **Issue 4: Navigation Issues**
```
Possible Cause: ViewModel factory
Solution: Check ViewModelProvider setup
```

## ✅ Success Criteria

Aplikasi dianggap berhasil jika:
- ✅ Launch tanpa crash
- ✅ Navigation antar screen lancar
- ✅ CRUD operations bekerja
- ✅ Data persistent setelah restart
- ✅ Search functionality responsive
- ✅ Form validation bekerja
- ✅ UI sesuai Material Design 3

## 📊 Testing Checklist

- [ ] App launches successfully
- [ ] Main screen displays correctly
- [ ] Staff list loads with sample data
- [ ] Siswa list loads with sample data
- [ ] Add new staff works
- [ ] Add new siswa works
- [ ] Form validation works
- [ ] Search functionality works
- [ ] Data persists after app restart
- [ ] Navigation works smoothly
- [ ] No crashes during normal usage
