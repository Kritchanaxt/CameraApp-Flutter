# 📷 CameraApp-Flutter

แอปพลิเคชันกล้องถ่ายรูปที่สร้างด้วย Flutter รองรับการถ่ายรูปจากกล้อง, เลือกรูปจากแกลเลอรี่ และ Crop รูปภาพได้

---

## 📸 Screenshots

<p align="center">
  <img src="https://github.com/Kritchanaxt/CameraApp-Flutter/blob/main/Screenshot_2025-05-22-14-58-18-31_f165245e62ddf8a25c583f178d0a3269.jpg" width="200" />
  <img src="https://github.com/Kritchanaxt/CameraApp-Flutter/blob/main/Screenshot%202568-05-22%20at%2014.42.56.png" width="220" />
  <img src="https://github.com/Kritchanaxt/CameraApp-Flutter/blob/main/Screenshot%202568-05-22%20at%2014.42.22.png" width="220" />
</p>

---

## ✨ Features

- 📷 **ถ่ายรูปจากกล้อง** - ใช้กล้องของอุปกรณ์ถ่ายรูป
- 🖼️ **เลือกรูปจากแกลเลอรี่** - เลือกรูปภาพจากคลังรูปภาพ
- ✂️ **Crop รูปภาพ** - ตัดรูปภาพตามอัตราส่วนที่ต้องการ
- 🔍 **Zoom รูปภาพ** - ขยายดูรูปภาพด้วย Interactive Viewer
- 🔐 **จัดการ Permissions** - ขอสิทธิ์การใช้งานกล้องและแกลเลอรี่อัตโนมัติ

---

## 🛠️ Technologies & Dependencies

| Package | Version | Description |
|---------|---------|-------------|
| [image_picker](https://pub.dev/packages/image_picker) | ^0.8.4+4 | เลือกรูปจากกล้องหรือแกลเลอรี่ |
| [image_cropper](https://pub.dev/packages/image_cropper) | ^9.0.0 | Crop รูปภาพ |
| [camera](https://pub.dev/packages/camera) | ^0.11.1 | ควบคุมกล้องแบบ native |
| [path_provider](https://pub.dev/packages/path_provider) | ^2.1.2 | จัดการ path ของไฟล์ |
| [permission_handler](https://pub.dev/packages/permission_handler) | ^11.0.1 | จัดการ permissions |

**Flutter SDK:** ^3.7.0

---

## 📁 Project Structure

```
flutter_cameraApp/
├── lib/
│   ├── main.dart                 # Entry point ของแอป
│   └── demo1/
│       ├── main_page.dart        # หน้าหลักสำหรับเลือกรูปหรือถ่ายรูป
│       └── cropped_image.dart    # หน้าแสดงรูปที่ crop แล้ว
├── android/
│   └── app/src/main/
│       └── AndroidManifest.xml   # ตั้งค่า permissions สำหรับ Android
├── ios/
│   └── Runner/
│       └── Info.plist            # ตั้งค่า permissions สำหรับ iOS
├── test/
│   └── widget_test.dart          # Widget tests
└── pubspec.yaml                  # Dependencies และ project config
```

---

## 🚀 Installation

### Prerequisites

- [Flutter SDK](https://docs.flutter.dev/get-started/install) (>= 3.7.0)
- [Android Studio](https://developer.android.com/studio) หรือ [Xcode](https://developer.apple.com/xcode/) (สำหรับ iOS)
- อุปกรณ์จริงหรือ Emulator/Simulator

### Step-by-step Setup

#### 1. Clone Repository

```bash
git clone https://github.com/Kritchanaxt/CameraApp-Flutter.git
cd CameraApp-Flutter/flutter_cameraApp
```

#### 2. ติดตั้ง Dependencies

```bash
flutter pub get
```

#### 3. ตรวจสอบสถานะ Flutter

```bash
flutter doctor
```

ตรวจสอบให้แน่ใจว่าทุกอย่างพร้อมใช้งาน (มีเครื่องหมาย ✓)

---

## 📱 Platform-Specific Setup

### Android Setup

Permissions ได้ถูกตั้งค่าไว้แล้วใน `android/app/src/main/AndroidManifest.xml`:

```xml
<uses-permission android:name="android.permission.CAMERA"/>
<uses-permission android:name="android.permission.RECORD_AUDIO"/>
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
```

### iOS Setup

Permissions ได้ถูกตั้งค่าไว้แล้วใน `ios/Runner/Info.plist`:

```xml
<key>NSPhotoLibraryUsageDescription</key>
<string>We need access to your photo library to select images.</string>

<key>NSCameraUsageDescription</key>
<string>We need access to the camera to record video.</string>

<key>NSMicrophoneUsageDescription</key>
<string>We need access to the microphone to record audio.</string>
```

สำหรับ iOS ต้องติดตั้ง CocoaPods ด้วย:

```bash
cd ios
pod install
cd ..
```

---

## ▶️ Running the App

### Android

```bash
# เชื่อมต่ออุปกรณ์ Android หรือเปิด Emulator
flutter run
```

### iOS

```bash
# เปิด Simulator หรือเชื่อมต่อ iPhone
flutter run
```

### เลือกอุปกรณ์เฉพาะ

```bash
# ดูรายการอุปกรณ์ที่เชื่อมต่อ
flutter devices

# รันบนอุปกรณ์เฉพาะ
flutter run -d <device_id>
```

### Build APK (Android)

```bash
# Debug APK
flutter build apk --debug

# Release APK
flutter build apk --release
```

### Build IPA (iOS)

```bash
flutter build ios --release
```

---

## 🧪 Testing

### Run All Tests

```bash
flutter test
```

### Run Specific Test File

```bash
flutter test test/widget_test.dart
```

### Run Tests with Coverage

```bash
flutter test --coverage
```

### ตัวอย่าง Widget Test

```dart
import 'package:flutter/material.dart';
import 'package:flutter_test/flutter_test.dart';
import 'package:flutter_camerapp/main.dart';

void main() {
  testWidgets('App should render MyApp widget', (WidgetTester tester) async {
    await tester.pumpWidget(const MyApp());
    
    // ตรวจสอบว่า AppBar มี title "Camera App"
    expect(find.text('Camera App'), findsOneWidget);
    
    // ตรวจสอบว่ามีปุ่ม Pick Gallery
    expect(find.text('Pick Gallery'), findsOneWidget);
    
    // ตรวจสอบว่ามีปุ่ม Capture Camera
    expect(find.text('Capture Camera'), findsOneWidget);
  });
}
```

---

## 📖 Usage Guide

### 1. เลือกรูปจากแกลเลอรี่

1. เปิดแอป
2. กดปุ่ม **"Pick Gallery"** (สีฟ้า)
3. เลือกรูปภาพจากแกลเลอรี่
4. Crop รูปภาพตามต้องการ
5. ดูรูปที่ crop แล้ว

### 2. ถ่ายรูปจากกล้อง

1. เปิดแอป
2. กดปุ่ม **"Capture Camera"** (สีม่วง)
3. อนุญาตการใช้งานกล้อง (ถ้าถูกถาม)
4. ถ่ายรูป
5. Crop รูปภาพตามต้องการ
6. ดูรูปที่ crop แล้ว

### 3. Crop รูปภาพ

- ลากเพื่อย้ายกรอบ crop
- ลาก corner เพื่อปรับขนาด
- ใช้ slider ปรับ rotation
- กด ✓ เพื่อยืนยัน หรือ ✕ เพื่อยกเลิก

---

## 🔧 Troubleshooting

### ปัญหาที่พบบ่อย

#### 1. Permission Denied

```
❌ แอปไม่สามารถใช้กล้องหรือแกลเลอรี่ได้
```

**วิธีแก้:**
- ไปที่ Settings > Apps > Camera App > Permissions
- เปิดใช้งาน Camera และ Storage permissions

#### 2. Gradle Build Failed (Android)

```bash
# ลองล้าง cache แล้ว build ใหม่
flutter clean
flutter pub get
flutter run
```

#### 3. CocoaPods Error (iOS)

```bash
cd ios
pod deintegrate
pod install
cd ..
flutter run
```

#### 4. Flutter Doctor Issues

```bash
flutter doctor -v
# ทำตามคำแนะนำที่แสดง
```

---

## 🔗 Links

- 🎥 [**Demo Video**](https://drive.google.com/file/d/1-8s6bqldvZhAcmpYjZn-cJcgSHelpf8U/view?usp=sharing)
- 📲 [**Download APK**](https://drive.google.com/file/d/1Uk1yse714hrWseSyQv5GgqLT-3oYMB1r/view?usp=sharing)
- 📦 [Flutter Documentation](https://docs.flutter.dev/)
- 📸 [image_picker Package](https://pub.dev/packages/image_picker)
- ✂️ [image_cropper Package](https://pub.dev/packages/image_cropper)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 👤 Author

**Kritchanaxt**

- GitHub: [@Kritchanaxt](https://github.com/Kritchanaxt)

---

⭐ หากโปรเจคนี้มีประโยชน์ อย่าลืมกด Star ให้ด้วยนะครับ!
