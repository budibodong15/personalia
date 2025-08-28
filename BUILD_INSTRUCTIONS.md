# 🔧 Panduan Build APK Tanpa Android Studio

## Metode 1: Online Build Service

### **1. GitHub Actions (Recommended)**
```yaml
# Buat file: .github/workflows/build.yml
name: Build APK
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: actions/setup-java@v3
      with:
        java-version: '11'
        distribution: 'temurin'
    - name: Build APK
      run: ./gradlew assembleDebug
    - name: Upload APK
      uses: actions/upload-artifact@v3
      with:
        name: app-debug
        path: app/build/outputs/apk/debug/app-debug.apk
```

### **2. Menggunakan Gitpod/Codespaces**
```bash
# Buka di browser:
https://gitpod.io/#https://github.com/your-repo/personalia

# Atau GitHub Codespaces:
# Buka repo di GitHub → Code → Codespaces → Create
```

## Metode 2: Local Build (Windows)

### **1. Install Java JDK**
```powershell
# Download dari: https://adoptium.net/
# Install JDK 11 atau 17
# Set environment variable:
$env:JAVA_HOME = "C:\Program Files\Eclipse Adoptium\jdk-11.x.x.x-hotspot"
```

### **2. Build APK**
```powershell
# Di folder project:
cd d:\personalia\personalia

# Build debug APK:
.\gradlew.bat assembleDebug

# APK akan tersimpan di:
# app\build\outputs\apk\debug\app-debug.apk
```

### **3. Install ke Android**
```powershell
# Enable Developer Options & USB Debugging di Android
# Connect via USB

# Install APK:
adb install app\build\outputs\apk\debug\app-debug.apk

# Atau copy APK ke phone dan install manual
```

## Metode 3: Docker Build

### **1. Buat Dockerfile**
```dockerfile
FROM openjdk:11-jdk

# Install Android SDK
RUN apt-get update && apt-get install -y wget unzip
RUN wget https://dl.google.com/android/repository/commandlinetools-linux-8512546_latest.zip
RUN unzip commandlinetools-linux-8512546_latest.zip
RUN mkdir -p /android-sdk/cmdline-tools/latest
RUN mv cmdline-tools/* /android-sdk/cmdline-tools/latest/

ENV ANDROID_HOME=/android-sdk
ENV PATH=$PATH:$ANDROID_HOME/cmdline-tools/latest/bin

# Accept licenses
RUN yes | sdkmanager --licenses

# Install build tools
RUN sdkmanager "build-tools;34.0.0" "platforms;android-34"

WORKDIR /app
COPY . .
RUN ./gradlew assembleDebug
```

### **2. Build dengan Docker**
```bash
# Build image:
docker build -t personalia-build .

# Extract APK:
docker run --rm -v $(pwd)/output:/output personalia-build cp app/build/outputs/apk/debug/app-debug.apk /output/
```

## Metode 4: Cloud Build Services

### **1. Firebase App Distribution**
```bash
# Install Firebase CLI:
npm install -g firebase-tools

# Login:
firebase login

# Deploy:
firebase appdistribution:distribute app-debug.apk --app YOUR_APP_ID
```

### **2. Microsoft App Center**
```bash
# Install App Center CLI:
npm install -g appcenter-cli

# Login:
appcenter login

# Distribute:
appcenter distribute release --app your-org/your-app --file app-debug.apk
```

## Quick Test Tanpa Build

Jika semua metode di atas sulit, saya bisa:

### **1. Buat Mock APK**
- Simulasi UI dengan screenshots
- Demo video functionality
- Interactive prototype

### **2. Web Version**
- Convert ke Progressive Web App
- Test di browser
- Same functionality, different platform

### **3. Code Review**
- Static analysis
- Logic verification
- Potential issue identification

## Troubleshooting

### **Error: JAVA_HOME not set**
```powershell
# Check Java installation:
java -version

# Set JAVA_HOME:
[Environment]::SetEnvironmentVariable("JAVA_HOME", "C:\Program Files\Java\jdk-11.x.x", "User")
```

### **Error: Android SDK not found**
```bash
# Download command line tools:
# https://developer.android.com/studio#command-tools

# Set ANDROID_HOME:
export ANDROID_HOME=/path/to/android-sdk
```

### **Error: Gradle build failed**
```bash
# Clean and retry:
./gradlew clean
./gradlew assembleDebug --stacktrace
```

## Rekomendasi

**Untuk Testing Cepat:**
1. ✅ Android Studio (paling mudah)
2. ✅ GitHub Actions (otomatis)
3. ✅ Online IDE (Gitpod/Codespaces)

**Untuk Production:**
1. ✅ Local build dengan proper signing
2. ✅ CI/CD pipeline
3. ✅ Play Store upload
