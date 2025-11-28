# 📷 CameraApp-Flutter

A camera application built with Flutter that supports capturing photos from camera, picking images from gallery, and cropping images.

---

## 📸 Screenshots

<p align="center">
  <img src="https://github.com/Kritchanaxt/CameraApp-Flutter/blob/main/Screenshot_2025-05-22-14-58-18-31_f165245e62ddf8a25c583f178d0a3269.jpg" width="200" />
  <img src="https://github.com/Kritchanaxt/CameraApp-Flutter/blob/main/Screenshot%202568-05-22%20at%2014.42.56.png" width="220" />
  <img src="https://github.com/Kritchanaxt/CameraApp-Flutter/blob/main/Screenshot%202568-05-22%20at%2014.42.22.png" width="220" />
</p>

---

## ✨ Features

- 📷 **Capture from Camera** - Take photos using device camera
- 🖼️ **Pick from Gallery** - Select images from photo library
- ✂️ **Image Cropping** - Crop images with custom aspect ratio
- 🔍 **Zoom Image** - Zoom and pan images with Interactive Viewer
- 🔐 **Permission Handling** - Automatic camera and gallery permission requests

---

## 🛠️ Technologies & Dependencies

| Package | Version | Description |
|---------|---------|-------------|
| [image_picker](https://pub.dev/packages/image_picker) | ^0.8.4+4 | Pick images from camera or gallery |
| [image_cropper](https://pub.dev/packages/image_cropper) | ^9.0.0 | Crop images |
| [camera](https://pub.dev/packages/camera) | ^0.11.1 | Native camera control |
| [path_provider](https://pub.dev/packages/path_provider) | ^2.1.2 | File path management |
| [permission_handler](https://pub.dev/packages/permission_handler) | ^11.0.1 | Permission handling |

**Flutter SDK:** ^3.7.0

---

## 📁 Project Structure

```
flutter_cameraApp/
├── lib/
│   ├── main.dart                 # App entry point
│   └── demo1/
│       ├── main_page.dart        # Main page for picking or capturing images
│       └── cropped_image.dart    # Page to display cropped image
├── android/
│   └── app/src/main/
│       └── AndroidManifest.xml   # Android permissions configuration
├── ios/
│   └── Runner/
│       └── Info.plist            # iOS permissions configuration
├── test/
│   └── widget_test.dart          # Widget tests
└── pubspec.yaml                  # Dependencies and project config
```

---

## 🚀 Installation

### Prerequisites

- [Flutter SDK](https://docs.flutter.dev/get-started/install) (>= 3.7.0)
- [Android Studio](https://developer.android.com/studio) or [Xcode](https://developer.apple.com/xcode/) (for iOS)
- Physical device or Emulator/Simulator

### Step-by-step Setup

#### 1. Clone Repository

```bash
git clone https://github.com/Kritchanaxt/CameraApp-Flutter.git
cd CameraApp-Flutter/flutter_cameraApp
```

#### 2. Install Dependencies

```bash
flutter pub get
```

#### 3. Check Flutter Status

```bash
flutter doctor
```

Make sure everything is ready (all items have ✓ checkmarks)

---

## 📱 Platform-Specific Setup

### Android Setup

Permissions are already configured in `android/app/src/main/AndroidManifest.xml`:

```xml
<uses-permission android:name="android.permission.CAMERA"/>
<uses-permission android:name="android.permission.RECORD_AUDIO"/>
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
```

### iOS Setup

Permissions are already configured in `ios/Runner/Info.plist`:

```xml
<key>NSPhotoLibraryUsageDescription</key>
<string>We need access to your photo library to select images.</string>

<key>NSCameraUsageDescription</key>
<string>We need access to the camera to record video.</string>

<key>NSMicrophoneUsageDescription</key>
<string>We need access to the microphone to record audio.</string>
```

For iOS, you also need to install CocoaPods:

```bash
cd ios
pod install
cd ..
```

---

## ▶️ Running the App

### Android

```bash
# Connect Android device or start Emulator
flutter run
```

### iOS

```bash
# Start Simulator or connect iPhone
flutter run
```

### Select Specific Device

```bash
# List connected devices
flutter devices

# Run on specific device
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

### Widget Test Example

```dart
import 'package:flutter/material.dart';
import 'package:flutter_test/flutter_test.dart';
import 'package:flutter_camerapp/main.dart';

void main() {
  testWidgets('App should render MyApp widget', (WidgetTester tester) async {
    await tester.pumpWidget(const MyApp());
    
    // Verify AppBar has title "Camera App"
    expect(find.text('Camera App'), findsOneWidget);
    
    // Verify Pick Gallery button exists
    expect(find.text('Pick Gallery'), findsOneWidget);
    
    // Verify Capture Camera button exists
    expect(find.text('Capture Camera'), findsOneWidget);
  });
}
```

---

## 📖 Usage Guide

### 1. Pick Image from Gallery

1. Open the app
2. Tap **"Pick Gallery"** button (blue)
3. Select an image from gallery
4. Crop the image as desired
5. View the cropped image

### 2. Capture from Camera

1. Open the app
2. Tap **"Capture Camera"** button (purple)
3. Grant camera permission (if prompted)
4. Take a photo
5. Crop the image as desired
6. View the cropped image

### 3. Crop Image

- Drag to move the crop frame
- Drag corners to resize
- Use slider to adjust rotation
- Tap ✓ to confirm or ✕ to cancel

---

## 🔧 Troubleshooting

### Common Issues

#### 1. Permission Denied

```
❌ App cannot access camera or gallery
```

**Solution:**
- Go to Settings > Apps > Camera App > Permissions
- Enable Camera and Storage permissions

#### 2. Gradle Build Failed (Android)

```bash
# Try clearing cache and rebuild
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
# Follow the instructions shown
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

⭐ If you find this project useful, don't forget to give it a Star!
