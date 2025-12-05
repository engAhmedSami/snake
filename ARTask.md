# ARTASK - 3D Model Viewer Application
## عارض النماذج ثلاثية الأبعاد مع تخصيص الألوان

[![Flutter](https://img.shields.io/badge/Flutter-3.38.0+-02569B?logo=flutter)](https://flutter.dev)
[![Dart](https://img.shields.io/badge/Dart-3.10.0+-0175C2?logo=dart)](https://dart.dev)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 📋 جدول المحتويات | Table of Contents

- [نظرة عامة | Overview](#overview)
- [المميزات الرئيسية | Key Features](#features)
- [لقطات الشاشة | Screenshots](#screenshots)
- [التقنيات المستخدمة | Technologies](#technologies)
- [متطلبات التشغيل | Requirements](#requirements)
- [التثبيت والتشغيل | Installation](#installation)
- [البنية المعمارية | Architecture](#architecture)
- [الملفات الرئيسية | Main Files](#main-files)
- [المكتبات المستخدمة | Dependencies](#dependencies)
- [المنصات المدعومة | Supported Platforms](#platforms)
- [التكوينات | Configuration](#configuration)
- [استخدام التطبيق | Usage](#usage)
- [التفاصيل التقنية | Technical Details](#technical)
- [التطوير المستقبلي | Future Enhancements](#future)
- [المساهمة | Contributing](#contributing)
- [الترخيص | License](#license)

---

## 🎯 نظرة عامة | Overview <a name="overview"></a>

### العربية

*ARTASK* هو تطبيق متطور مبني بتقنية Flutter لعرض النماذج ثلاثية الأبعاد (3D Models) مع إمكانية تخصيص الألوان بشكل تفاعلي. يوفر التطبيق تجربة مستخدم سلسة وحديثة لعرض وتحريك النماذج ثلاثية الأبعاد بصيغة GLB مع القدرة على تغيير ألوانها بشكل فوري.

تم تطوير هذا المشروع كجزء من مشروع تخرج، ويستخدم تقنيات الويب الحديثة (model-viewer.js) من خلال WebView لعرض النماذج ثلاثية الأبعاد، مما يوفر أداءً ممتازاً عبر جميع المنصات.

### English

*ARTASK* is an advanced Flutter application for viewing 3D models with interactive color customization. The app provides a smooth and modern user experience for displaying and manipulating GLB format 3D models with the ability to change their colors in real-time.

Developed as a graduation project, it utilizes modern web technologies (model-viewer.js) through WebView to render 3D models, providing excellent performance across all platforms.

---

## ✨ المميزات الرئيسية | Key Features <a name="features"></a>

### العربية

#### 🎨 عرض النماذج ثلاثية الأبعاد
- *عرض تفاعلي كامل*: إمكانية تدوير النموذج 360 درجة باستخدام اللمس
- *تكبير وتصغير*: التحكم الكامل في حجم وزاوية العرض
- *دوران تلقائي*: ميزة الدوران التلقائي لعرض النموذج من جميع الزوايا
- *تحميل سريع*: تحميل فوري للنماذج بدون تأخير
- *خلفية داكنة احترافية*: تصميم أنيق يبرز تفاصيل النموذج

#### 🌈 تخصيص الألوان الديناميكي
- *10 ألوان جاهزة*: لوحة ألوان متنوعة (أبيض، أحمر، أزرق، أخضر، أصفر، برتقالي، بنفسجي، وردي، فيروزي، بني)
- *تطبيق فوري*: تغيير اللون يحدث مباشرة على النموذج
- *عرض الكود اللوني*: إظهار الكود الست عشري (Hex) لكل لون
- *تأثيرات بصرية*: إضاءة وتأثيرات على اللون المختار
- *واجهة سلسة*: اختيار الألوان بسهولة من خلال شريط أفقي قابل للتمرير

#### 🎯 واجهة المستخدم الحديثة
- *Material Design 3*: تصميم عصري يتبع أحدث معايير Google
- *وضع داكن*: واجهة مريحة للعين
- *تصميم متجاوب*: يعمل بكفاءة على جميع أحجام الشاشات
- *رسوم متحركة سلسة*: انتقالات وحركات طبيعية
- *سهولة الاستخدام*: واجهة بسيطة وبديهية

### English

#### 🎨 3D Model Viewing
- *Full Interactive Display*: 360-degree model rotation using touch controls
- *Zoom & Pan*: Complete control over size and viewing angle
- *Auto-Rotation*: Automatic rotation feature to display model from all angles
- *Fast Loading*: Instant model loading without delays
- *Professional Dark Background*: Elegant design highlighting model details

#### 🌈 Dynamic Color Customization
- *10 Preset Colors*: Diverse color palette (White, Red, Blue, Green, Yellow, Orange, Purple, Pink, Teal, Brown)
- *Instant Application*: Color changes happen directly on the model
- *Hex Code Display*: Shows hexadecimal code for each color
- *Visual Effects*: Lighting and effects on selected color
- *Smooth Interface*: Easy color selection through horizontal scrollable bar

#### 🎯 Modern User Interface
- *Material Design 3*: Contemporary design following latest Google standards
- *Dark Mode*: Eye-comfortable interface
- *Responsive Design*: Works efficiently on all screen sizes
- *Smooth Animations*: Natural transitions and movements
- *User-Friendly*: Simple and intuitive interface

---

## 📸 لقطات الشاشة | Screenshots <a name="screenshots"></a>


[يمكن إضافة لقطات الشاشة هنا]
[Screenshots can be added here]


---

## 🛠 التقنيات المستخدمة | Technologies <a name="technologies"></a>

### العربية

| التقنية | الوصف | الإصدار |
|---------|--------|---------|
| *Flutter* | إطار عمل تطوير التطبيقات متعدد المنصات | 3.38.0+ |
| *Dart* | لغة البرمجة الأساسية | 3.10.0+ |
| *model-viewer.js* | مكتبة عرض النماذج ثلاثية الأبعاد (Web) | من خلال model_viewer_plus |
| *WebView* | عرض محتوى الويب داخل التطبيق | 4.13.0 |
| *GLB Format* | صيغة الملفات ثلاثية الأبعاد (Binary glTF) | - |
| *Material Design 3* | نظام التصميم من Google | - |
| *JavaScript Bridge* | التواصل بين Flutter و WebView | - |

### English

| Technology | Description | Version |
|------------|-------------|---------|
| *Flutter* | Cross-platform app development framework | 3.38.0+ |
| *Dart* | Primary programming language | 3.10.0+ |
| *model-viewer.js* | 3D model viewing library (Web) | via model_viewer_plus |
| *WebView* | Display web content inside app | 4.13.0 |
| *GLB Format* | 3D file format (Binary glTF) | - |
| *Material Design 3* | Google's design system | - |
| *JavaScript Bridge* | Communication between Flutter & WebView | - |

---

## 📦 متطلبات التشغيل | Requirements <a name="requirements"></a>

### العربية

#### المتطلبات الأساسية:
- *Flutter SDK*: الإصدار 3.38.0 أو أحدث
- *Dart SDK*: الإصدار 3.10.0 أو أحدث
- *Android Studio* أو *VS Code* (للتطوير)
- *Git* (لاستنساخ المشروع)

#### متطلبات المنصات:

*Android:*
- Android SDK: API Level 21+ (Android 5.0+)
- Java: JDK 17
- Gradle: 7.5+
- Kotlin: 1.9.0+

*iOS:*
- Xcode: 14.0+
- iOS: 12.0+
- CocoaPods: مثبت
- macOS للتطوير

*Web:*
- متصفح حديث يدعم WebGL
- Chrome, Firefox, Safari, Edge

*Desktop (Windows/macOS/Linux):*
- الإصدارات المدعومة من أنظمة التشغيل
- متطلبات Flutter Desktop

### English

#### Basic Requirements:
- *Flutter SDK*: Version 3.38.0 or higher
- *Dart SDK*: Version 3.10.0 or higher
- *Android Studio* or *VS Code* (for development)
- *Git* (to clone project)

#### Platform Requirements:

*Android:*
- Android SDK: API Level 21+ (Android 5.0+)
- Java: JDK 17
- Gradle: 7.5+
- Kotlin: 1.9.0+

*iOS:*
- Xcode: 14.0+
- iOS: 12.0+
- CocoaPods: installed
- macOS for development

*Web:*
- Modern browser with WebGL support
- Chrome, Firefox, Safari, Edge

*Desktop (Windows/macOS/Linux):*
- Supported OS versions
- Flutter Desktop requirements

---

## 🚀 التثبيت والتشغيل | Installation <a name="installation"></a>

### العربية

#### 1. استنساخ المشروع

bash
git clone https://github.com/yourusername/artask.git
cd artask


#### 2. تثبيت المكتبات

bash
flutter pub get


#### 3. التحقق من البيئة

bash
flutter doctor


تأكد من أن جميع العلامات خضراء للمنصة التي تريد تشغيل التطبيق عليها.

#### 4. تشغيل التطبيق

*على Android:*
bash
flutter run -d android


*على iOS:*
bash
flutter run -d ios


*على الويب:*
bash
flutter run -d chrome


*على Windows:*
bash
flutter run -d windows


#### 5. بناء التطبيق (للنشر)

*Android (APK):*
bash
flutter build apk --release


*Android (App Bundle):*
bash
flutter build appbundle --release


*iOS:*
bash
flutter build ios --release


*Web:*
bash
flutter build web --release


*Windows:*
bash
flutter build windows --release


### English

#### 1. Clone the Project

bash
git clone https://github.com/yourusername/artask.git
cd artask


#### 2. Install Dependencies

bash
flutter pub get


#### 3. Verify Environment

bash
flutter doctor


Ensure all checkmarks are green for the platform you want to run the app on.

#### 4. Run the App

*On Android:*
bash
flutter run -d android


*On iOS:*
bash
flutter run -d ios


*On Web:*
bash
flutter run -d chrome


*On Windows:*
bash
flutter run -d windows


#### 5. Build for Production

*Android (APK):*
bash
flutter build apk --release


*Android (App Bundle):*
bash
flutter build appbundle --release


*iOS:*
bash
flutter build ios --release


*Web:*
bash
flutter build web --release


*Windows:*
bash
flutter build windows --release


---

## 🏗 البنية المعمارية | Architecture <a name="architecture"></a>

### العربية

#### هيكل المشروع


artask/
├── lib/
│   ├── main.dart                 # نقطة البداية - تشغيل التطبيق
│   ├── my_app.dart              # إعدادات التطبيق والثيم
│   └── home_view.dart           # الشاشة الرئيسية - عارض النماذج
├── assets/
│   └── models/
│       └── model.glb            # النموذج ثلاثي الأبعاد (3.1 MB)
├── android/                     # ملفات Android
├── ios/                         # ملفات iOS
├── web/                         # ملفات Web
├── windows/                     # ملفات Windows
├── macos/                       # ملفات macOS
├── linux/                       # ملفات Linux
├── pubspec.yaml                 # المكتبات والأصول
└── README.md                    # هذا الملف


#### معمارية الكود


┌─────────────────────────────────────────┐
│            main.dart                    │
│  (Entry Point - System UI Setup)       │
└──────────────┬──────────────────────────┘
               │
               ▼
┌─────────────────────────────────────────┐
│           my_app.dart                   │
│  (App Configuration & Theme)            │
│  • Material 3 Dark Theme                │
│  • Color Scheme (#6366F1)               │
│  • Background (#0A0A0A)                 │
└──────────────┬──────────────────────────┘
               │
               ▼
┌─────────────────────────────────────────┐
│          home_view.dart                 │
│  (Main Feature Screen - 249 lines)     │
│                                         │
│  ┌────────────────────────────────┐    │
│  │   ModelViewer Widget           │    │
│  │   • WebView Integration        │    │
│  │   • model-viewer.js            │    │
│  │   • 3D Model Rendering         │    │
│  └────────────┬───────────────────┘    │
│               │                         │
│               ▼                         │
│  ┌────────────────────────────────┐    │
│  │   JavaScript Bridge            │    │
│  │   • Color Conversion           │    │
│  │   • Material Updates           │    │
│  │   • Async Execution            │    │
│  └────────────┬───────────────────┘    │
│               │                         │
│               ▼                         │
│  ┌────────────────────────────────┐    │
│  │   Color Picker UI              │    │
│  │   • 10 Color Palette           │    │
│  │   • Selection State            │    │
│  │   • Visual Feedback            │    │
│  └────────────────────────────────┘    │
└─────────────────────────────────────────┘


#### نمط الحالة (State Management)

- *StatefulWidget*: إدارة محلية للحالة
- *Local State*: حفظ اللون المختار
- *WebViewController*: التحكم في WebView
- *JavaScript Evaluation*: تنفيذ أكواد JavaScript

### English

#### Project Structure


artask/
├── lib/
│   ├── main.dart                 # Entry point - App launch
│   ├── my_app.dart              # App settings and theme
│   └── home_view.dart           # Main screen - Model viewer
├── assets/
│   └── models/
│       └── model.glb            # 3D Model (3.1 MB)
├── android/                     # Android files
├── ios/                         # iOS files
├── web/                         # Web files
├── windows/                     # Windows files
├── macos/                       # macOS files
├── linux/                       # Linux files
├── pubspec.yaml                 # Dependencies and assets
└── README.md                    # This file


#### Code Architecture

[Same diagram as Arabic section]

#### State Management Pattern

- *StatefulWidget*: Local state management
- *Local State*: Stores selected color
- *WebViewController*: Controls WebView
- *JavaScript Evaluation*: Executes JavaScript code

---

## 📄 الملفات الرئيسية | Main Files <a name="main-files"></a>

### 1. [main.dart](lib/main.dart)

*العربية:*
- نقطة البداية للتطبيق
- إعداد شريط الحالة (Status Bar) شفاف
- تشغيل MyApp

*English:*
- Application entry point
- Configure transparent status bar
- Launch MyApp widget

dart
void main() {
  SystemChrome.setSystemUIOverlayStyle(
    const SystemUiOverlayStyle(statusBarColor: Colors.transparent),
  );
  runApp(const MyApp());
}


---

### 2. [my_app.dart](lib/my_app.dart)

*العربية:*
- تكوين التطبيق الرئيسي
- إعدادات Material Design 3
- الثيم الداكن مع اللون الأساسي #6366F1 (Indigo)
- التوجيه إلى HomeView

*English:*
- Main app configuration
- Material Design 3 settings
- Dark theme with primary color #6366F1 (Indigo)
- Routes to HomeView

dart
MaterialApp(
  theme: ThemeData(
    colorScheme: ColorScheme.fromSeed(
      seedColor: const Color(0xFF6366F1),
      brightness: Brightness.dark,
    ),
    scaffoldBackgroundColor: const Color(0xFF0A0A0A),
    useMaterial3: true,
  ),
  home: const HomeView(),
)


---

### 3. [home_view.dart](lib/home_view.dart) - *الملف الأهم*

*العربية:*
الشاشة الرئيسية للتطبيق (249 سطر) وتحتوي على:

#### المكونات:
1. *AppBar*: شريط العنوان
2. *ModelViewer Widget*: عارض النماذج ثلاثية الأبعاد
3. *Color Picker Panel*: لوحة اختيار الألوان
4. *JavaScript Bridge*: جسر التواصل مع WebView

#### الوظائف الرئيسية:

**_updateModelColor(Color color)**
- تحويل اللون من Flutter إلى WebGL RGB (0-1)
- حقن JavaScript في WebView
- تحديث جميع المواد (Materials) في النموذج

dart
Future<void> _updateModelColor(Color color) async {
  final r = color.red / 255.0;
  final g = color.green / 255.0;
  final b = color.blue / 255.0;

  final script = '''
    const modelViewer = document.querySelector('model-viewer');
    if (modelViewer && modelViewer.model) {
      modelViewer.model.materials.forEach(material => {
        material.pbrMetallicRoughness.setBaseColorFactor([$r, $g, $b, 1.0]);
      });
    }
  ''';

  await _webViewController.evaluateJavascript(source: script);
}


**_buildColorPicker()**
- بناء واجهة اختيار الألوان
- 10 ألوان جاهزة
- تأثيرات بصرية ورسوم متحركة

#### خصائص ModelViewer:
dart
ModelViewer(
  src: 'assets/models/model.glb',
  alt: 'A 3D model',
  ar: false,                    // AR معطل
  autoRotate: true,             // دوران تلقائي
  cameraControls: true,         // تحكم بالكاميرا
  loading: Loading.eager,       // تحميل فوري
  backgroundColor: Color(0xFF0A0A0A),
)


*English:*
Main application screen (249 lines) containing:

#### Components:
1. *AppBar*: Title bar
2. *ModelViewer Widget*: 3D model viewer
3. *Color Picker Panel*: Color selection panel
4. *JavaScript Bridge*: Communication bridge with WebView

#### Main Functions:

**_updateModelColor(Color color)**
- Converts color from Flutter to WebGL RGB (0-1)
- Injects JavaScript into WebView
- Updates all materials in the model

**_buildColorPicker()**
- Builds color picker UI
- 10 preset colors
- Visual effects and animations

---

## 📚 المكتبات المستخدمة | Dependencies <a name="dependencies"></a>

### العربية

#### المكتبات الأساسية

yaml
dependencies:
  flutter:
    sdk: flutter
  cupertino_icons: ^1.0.8      # أيقونات iOS
  model_viewer_plus: ^1.7.2    # عارض النماذج 3D (مثبت: 1.10.0)


#### المكتبات التبعية (Transitive Dependencies)

| المكتبة | الإصدار | الوظيفة |
|---------|---------|---------|
| webview_flutter | 4.13.0 | عرض WebView الأساسي |
| webview_flutter_android | 4.10.11 | WebView لأندرويد |
| webview_flutter_wkwebview | 3.23.5 | WebView لـ iOS |
| url_launcher | 6.3.2 | فتح الروابط |
| android_intent_plus | 6.0.0 | Android Intents |

#### مكتبات التطوير

yaml
dev_dependencies:
  flutter_test:
    sdk: flutter
  flutter_lints: ^6.0.0        # فحص جودة الكود


### English

#### Core Dependencies

yaml
dependencies:
  flutter:
    sdk: flutter
  cupertino_icons: ^1.0.8      # iOS icons
  model_viewer_plus: ^1.7.2    # 3D model viewer (installed: 1.10.0)


#### Transitive Dependencies

| Package | Version | Purpose |
|---------|---------|---------|
| webview_flutter | 4.13.0 | Core WebView display |
| webview_flutter_android | 4.10.11 | Android WebView |
| webview_flutter_wkwebview | 3.23.5 | iOS WebView |
| url_launcher | 6.3.2 | Open URLs |
| android_intent_plus | 6.0.0 | Android Intents |

#### Development Dependencies

yaml
dev_dependencies:
  flutter_test:
    sdk: flutter
  flutter_lints: ^6.0.0        # Code quality linting


---

## 🖥 المنصات المدعومة | Supported Platforms <a name="platforms"></a>

### العربية

| المنصة | الحالة | الملاحظات |
|--------|--------|-----------|
| ✅ *Android* | مدعوم كاملاً | الهدف الأساسي - API 21+ |
| ✅ *iOS* | مدعوم كاملاً | iOS 12.0+ |
| ✅ *Web* | مدعوم كاملاً | PWA قابل للتثبيت |
| ✅ *Windows* | مدعوم | Desktop |
| ✅ *macOS* | مدعوم | Desktop |
| ✅ *Linux* | مدعوم | Desktop |

### English

| Platform | Status | Notes |
|----------|--------|-------|
| ✅ *Android* | Fully Supported | Primary target - API 21+ |
| ✅ *iOS* | Fully Supported | iOS 12.0+ |
| ✅ *Web* | Fully Supported | Installable PWA |
| ✅ *Windows* | Supported | Desktop |
| ✅ *macOS* | Supported | Desktop |
| ✅ *Linux* | Supported | Desktop |

---

## ⚙ التكوينات | Configuration <a name="configuration"></a>

### العربية

#### Android Configuration
*الملف*: android/app/build.gradle.kts

kotlin
namespace = "com.example.artask"
applicationId = "com.example.artask"
minSdk = 21
targetSdk = flutter.targetSdkVersion
versionCode = flutter.versionCode
versionName = flutter.versionName


*الأذونات*:
xml
<uses-permission android:name="android.permission.INTERNET"/>


*إعدادات خاصة*:
- usesCleartextTraffic: true - للسماح بـ HTTP
- تسريع الأجهزة مفعل

#### iOS Configuration
*الملف*: ios/Runner/Info.plist

- Swift-based AppDelegate
- Plugin registration enabled
- Standard Flutter iOS setup

#### Web Configuration (PWA)

*الملف*: web/manifest.json

json
{
  "name": "artask",
  "short_name": "artask",
  "start_url": ".",
  "display": "standalone",
  "orientation": "portrait-primary",
  "theme_color": "#0175C2"
}


#### Assets Configuration

*الملف*: pubspec.yaml

yaml
flutter:
  assets:
    - assets/models/model.glb

  uses-material-design: true


### English

[Same configuration details as Arabic section]

---

## 💡 استخدام التطبيق | Usage <a name="usage"></a>

### العربية

#### الخطوات الأساسية:

1. *فتح التطبيق*
   - سيتم تحميل النموذج ثلاثي الأبعاد تلقائياً
   - النموذج سيبدأ بالدوران التلقائي

2. *التفاعل مع النموذج*
   - *التدوير*: اسحب بإصبع واحد لتدوير النموذج
   - *التكبير*: اسحب بإصبعين للتكبير والتصغير
   - *النقل*: استخدم إصبعين للتحرك حول النموذج

3. *تغيير اللون*
   - انتقل إلى لوحة الألوان في الأسفل
   - اختر أي لون من الألوان العشرة المتاحة
   - سيتم تطبيق اللون فوراً على النموذج

4. *معلومات اللون*
   - الكود الست عشري (Hex) يظهر أسفل كل لون
   - اللون المختار يظهر مع علامة صح وإضاءة خاصة

### English

#### Basic Steps:

1. *Open App*
   - 3D model loads automatically
   - Model starts auto-rotating

2. *Interact with Model*
   - *Rotate*: Drag with one finger to rotate
   - *Zoom*: Pinch with two fingers to zoom in/out
   - *Pan*: Use two fingers to move around

3. *Change Color*
   - Navigate to color panel at bottom
   - Select any of the 10 available colors
   - Color applies instantly to model

4. *Color Information*
   - Hex code displays below each color
   - Selected color shows checkmark and glow effect

---

## 🔧 التفاصيل التقنية | Technical Details <a name="technical"></a>

### العربية

#### كيف يعمل تغيير اللون؟

1. *اختيار اللون*: المستخدم يختار لون من الواجهة
2. *تحويل اللون*: تحويل Color من Flutter (0-255) إلى WebGL RGB (0-1)
3. *إنشاء كود JavaScript*: بناء سكريبت لتحديث المواد
4. *حقن الكود*: تنفيذ JavaScript في WebView
5. *تحديث النموذج*: جميع المواد في النموذج تُحدث

#### JavaScript Bridge Code

dart
Future<void> _updateModelColor(Color color) async {
  // تحويل القيم من 0-255 إلى 0-1
  final r = color.red / 255.0;
  final g = color.green / 255.0;
  final b = color.blue / 255.0;

  final script = '''
    (function() {
      const modelViewer = document.querySelector('model-viewer');
      if (modelViewer && modelViewer.model) {
        // تحديث كل المواد
        modelViewer.model.materials.forEach(material => {
          if (material.pbrMetallicRoughness) {
            material.pbrMetallicRoughness.setBaseColorFactor([$r, $g, $b, 1.0]);
          }
        });
      }
    })();
  ''';

  try {
    await _webViewController.evaluateJavascript(source: script);
  } catch (e) {
    print('Error updating color: $e');
  }
}


#### تأخير التحميل الأولي

dart
@override
void initState() {
  super.initState();
  // انتظار 1.5 ثانية لضمان تحميل النموذج
  Future.delayed(const Duration(milliseconds: 1500), () {
    if (mounted) {
      _updateModelColor(_selectedColor);
    }
  });
}


#### صيغة GLB (Binary glTF)

- *glTF*: GL Transmission Format
- *GLB*: النسخة الثنائية (Binary) من glTF
- *الحجم*: 3.1 MB
- *المحتوى*: Geometry + Materials + Textures
- *الميزة*: ملف واحد يحتوي على كل شيء

### English

#### How Does Color Changing Work?

1. *Color Selection*: User selects color from UI
2. *Color Conversion*: Convert Flutter Color (0-255) to WebGL RGB (0-1)
3. *JavaScript Code Creation*: Build script to update materials
4. *Code Injection*: Execute JavaScript in WebView
5. *Model Update*: All materials in model are updated

[Same code examples as Arabic section]

---

## 🚀 التطوير المستقبلي | Future Enhancements <a name="future"></a>

### العربية

#### الميزات المقترحة:

1. *إدارة النماذج*
   - رفع نماذج مخصصة من الجهاز
   - مكتبة نماذج متعددة
   - حفظ النماذج المفضلة

2. *تخصيص المواد*
   - ضبط الخشونة (Roughness)
   - ضبط المعدنية (Metallic)
   - ضبط الشفافية (Opacity)
   - إضافة أنماط (Textures)

3. *ميزات AR (الواقع المعزز)*
   - عرض النموذج في العالم الحقيقي
   - التقاط صور AR
   - مشاركة صور AR

4. *التخصيصات الإضافية*
   - منتقي ألوان كامل (Color Picker)
   - حفظ الألوان المخصصة
   - إعدادات الإضاءة
   - خلفيات مختلفة

5. *المشاركة والتصدير*
   - التقاط لقطات شاشة
   - مشاركة على وسائل التواصل
   - تصدير النموذج بالألوان المخصصة

6. *الأداء والتحسينات*
   - ضغط النماذج
   - تحميل تدريجي (Progressive Loading)
   - ذاكرة تخزين مؤقت (Caching)

7. *قاعدة البيانات*
   - حفظ الحالة (State Persistence)
   - سجل الألوان المستخدمة
   - المفضلات

8. *المصادقة*
   - تسجيل دخول المستخدمين
   - المزامنة السحابية
   - مشاركة النماذج

### English

#### Proposed Features:

1. *Model Management*
   - Upload custom models from device
   - Multiple model library
   - Save favorite models

2. *Material Customization*
   - Adjust roughness
   - Adjust metallic properties
   - Adjust opacity
   - Add textures

3. *AR Features (Augmented Reality)*
   - Display model in real world
   - Capture AR photos
   - Share AR images

4. *Additional Customizations*
   - Full color picker
   - Save custom colors
   - Lighting settings
   - Different backgrounds

5. *Sharing & Export*
   - Capture screenshots
   - Share on social media
   - Export model with custom colors

6. *Performance & Optimizations*
   - Model compression
   - Progressive loading
   - Caching

7. *Database*
   - State persistence
   - Color history
   - Favorites

8. *Authentication*
   - User login
   - Cloud sync
   - Model sharing

---

## 👥 المساهمة | Contributing <a name="contributing"></a>

### العربية

نرحب بالمساهمات! إذا كنت ترغب في تحسين المشروع:

1. *Fork* المشروع
2. أنشئ *فرع* جديد (git checkout -b feature/AmazingFeature)
3. *Commit* تغييراتك (git commit -m 'Add some AmazingFeature')
4. *Push* إلى الفرع (git push origin feature/AmazingFeature)
5. افتح *Pull Request*

#### قواعد المساهمة:

- اتبع معايير Dart/Flutter coding style
- أضف تعليقات واضحة للكود
- اختبر التغييرات قبل الـ PR
- حدّث الـ README إذا لزم الأمر

### English

We welcome contributions! If you'd like to improve the project:

1. *Fork* the project
2. Create a new *branch* (git checkout -b feature/AmazingFeature)
3. *Commit* your changes (git commit -m 'Add some AmazingFeature')
4. *Push* to the branch (git push origin feature/AmazingFeature)
5. Open a *Pull Request*

#### Contribution Guidelines:

- Follow Dart/Flutter coding standards
- Add clear code comments
- Test changes before PR
- Update README if necessary

---

## 📝 الترخيص | License <a name="license"></a>

### العربية

هذا المشروع مرخص تحت رخصة MIT - انظر ملف [LICENSE](LICENSE) للتفاصيل.

### English

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 📞 الاتصال | Contact <a name="contact"></a>

### العربية

*مشروع تخرج - ARTASK*

- *المطور*: [اسمك هنا]
- *البريد الإلكتروني*: [your.email@example.com]
- *GitHub*: [@yourusername](https://github.com/yourusername)
- *رابط المشروع*: [https://github.com/yourusername/artask](https://github.com/yourusername/artask)

### English

*Graduation Project - ARTASK*

- *Developer*: [Your Name Here]
- *Email*: [your.email@example.com]
- *GitHub*: [@yourusername](https://github.com/yourusername)
- *Project Link*: [https://github.com/yourusername/artask](https://github.com/yourusername/artask)

---

## 🙏 شكر وتقدير | Acknowledgments <a name="acknowledgments"></a>

### العربية

- *Flutter Team* - إطار العمل الرائع
- *Google* - مكتبة model-viewer.js
- *model_viewer_plus* - مكتبة Flutter wrapper
- جميع المساهمين في المكتبات مفتوحة المصدر المستخدمة

### English

- *Flutter Team* - Amazing framework
- *Google* - model-viewer.js library
- *model_viewer_plus* - Flutter wrapper library
- All contributors to open-source libraries used

---

## 📊 إحصائيات المشروع | Project Stats <a name="stats"></a>

### العربية

| العنصر | القيمة |
|--------|-------|
| *إجمالي عدد الملفات* | ~50+ ملف |
| *أسطر الكود* | ~400 سطر (Dart) |
| *حجم المشروع* | ~5.1 MB |
| *حجم النموذج 3D* | 3.1 MB |
| *المنصات المدعومة* | 6 منصات |
| *المكتبات الخارجية* | 3 مكتبات رئيسية |

### English

| Item | Value |
|------|-------|
| *Total Files* | ~50+ files |
| *Lines of Code* | ~400 lines (Dart) |
| *Project Size* | ~5.1 MB |
| *3D Model Size* | 3.1 MB |
| *Supported Platforms* | 6 platforms |
| *External Libraries* | 3 main packages |

---

## 🐛 المشاكل المعروفة | Known Issues <a name="issues"></a>

### العربية

1. *تأخير تطبيق اللون الأولي*: يوجد تأخير 1.5 ثانية عند بدء التطبيق لضمان تحميل النموذج
2. *عدم وجود معالجة أخطاء شاملة*: يمكن تحسين معالجة الأخطاء
3. *الاختبارات*: الاختبار الافتراضي يحتاج تحديث

### English

1. *Initial Color Delay*: 1.5-second delay on app start to ensure model loads
2. *Limited Error Handling*: Error handling can be improved
3. *Tests*: Default test needs updating

---

## 📚 موارد إضافية | Additional Resources <a name="resources"></a>

### العربية

#### وثائق مفيدة:

- [Flutter Documentation](https://docs.flutter.dev/)
- [model-viewer.js Docs](https://modelviewer.dev/)
- [model_viewer_plus Package](https://pub.dev/packages/model_viewer_plus)
- [WebView Flutter](https://pub.dev/packages/webview_flutter)
- [glTF Format Specification](https://www.khronos.org/gltf/)

#### أدوات مفيدة:

- [Blender](https://www.blender.org/) - إنشاء نماذج 3D
- [glTF Viewer](https://gltf-viewer.donmccurdy.com/) - معاينة ملفات GLB
- [Android Studio](https://developer.android.com/studio) - تطوير Android
- [Xcode](https://developer.apple.com/xcode/) - تطوير iOS

### English

#### Useful Documentation:

[Same links as Arabic section]

#### Useful Tools:

- [Blender](https://www.blender.org/) - Create 3D models
- [glTF Viewer](https://gltf-viewer.donmccurdy.com/) - Preview GLB files
- [Android Studio](https://developer.android.com/studio) - Android development
- [Xcode](https://developer.apple.com/xcode/) - iOS development

---

<div align="center">

## ⭐ إذا أعجبك المشروع، لا تنسى إضافة نجمة! | If you like this project, don't forget to star it!

*صنع بـ ❤ باستخدام Flutter*
*Made with ❤ using Flutter*

---

### 📱 مشروع تخرج متميز | Outstanding Graduation Project

</div>

---

*آخر تحديث | Last Updated*: ديسمبر 2025 | December 2025
*الإصدار | Version*: 1.0.0+1
