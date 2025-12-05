# توثيق شامل لمشروع لعبة Snake - Unity & Flutter Integration

## 📋 نظرة عامة على المشروع

هذا المشروع عبارة عن لعبة Snake كلاسيكية تم تطويرها باستخدام **Unity** لمنطق اللعبة والرسومات، ثم دمجها مع **Flutter** لإنشاء تطبيق Android كامل مع واجهة مستخدم احترافية.

---

## 🎯 البنية التقنية للمشروع

### 1. التقنيات المستخدمة

#### أ) Unity Engine
- **الإصدار**: Unity 6000.0
- **اللغة**: C#
- **الغرض**: تطوير منطق اللعبة، الفيزياء، والرسومات

#### ب) Flutter Framework
- **الإصدار**: SDK 3.10.3+
- **اللغة**: Dart
- **الغرض**: بناء واجهة المستخدم، التنقل بين الشاشات، وإدارة التطبيق

#### ج) Android Platform
- **Compile SDK**: 36
- **Min SDK**: 23 (Android 6.0)
- **Target SDK**: 36
- **Build Tools**: 36.0.0
- **NDK Version**: 27.2.12479018
- **Java Version**: 17

---

## 📦 الـ Packages والمكتبات المستخدمة

### 1. Flutter Packages (من pubspec.yaml)

#### **أ) flutter_embed_unity: ^1.4.0**
- **الوظيفة**: دمج Unity داخل تطبيق Flutter
- **الاستخدام**: عرض محتوى Unity كـ widget داخل Flutter
- **الأهمية**: هذا الـ package الأساسي الذي يسمح بالتكامل بين Unity و Flutter

#### **ب) flutter_embed_unity_6000_0_android: ^1.2.2**
- **الوظيفة**: دعم Unity 6000.0 على منصة Android
- **الاستخدام**: توفير التوافقية مع إصدار Unity الحديث
- **الأهمية**: ضروري لتشغيل Unity 6000.0 على Android

#### **ج) shared_preferences: ^2.2.2**
- **الوظيفة**: حفظ البيانات محلياً على الجهاز
- **الاستخدام**: حفظ أعلى نقاط (High Score) للاعب
- **التخزين**: يستخدم SharedPreferences على Android و UserDefaults على iOS
- **الكود المستخدم**:
  ```dart
  // حفظ High Score
  final prefs = await SharedPreferences.getInstance();
  await prefs.setInt('highScore', score);

  // قراءة High Score
  _highScore = prefs.getInt('highScore') ?? 0;
  ```

#### **د) cupertino_icons: ^1.0.8**
- **الوظيفة**: توفير أيقونات iOS style
- **الاستخدام**: أيقونات للواجهة (اختياري في المشروع)

### 2. Dev Dependencies

#### **flutter_lints: ^6.0.0**
- **الوظيفة**: تحليل الكود والتأكد من جودته
- **الفائدة**: يساعد في كتابة كود نظيف ومتوافق مع معايير Flutter

---

## 🎮 هيكل المشروع - Unity

### 1. السكريبتات الأساسية (Assets/Scripts)

#### **أ) GameController.cs**
**الوظيفة**: المتحكم الرئيسي في اللعبة

**المسؤوليات**:
- إدارة حالة اللعبة (بدء، نهاية، مؤقت)
- حساب النقاط والمستويات
- إنشاء الأعداء (Spikes) والبيض (Eggs)
- رسم الحدود (Walls/Rocks)
- التواصل مع Flutter

**الميزات الرئيسية**:
```csharp
// نظام المستويات
void LevelUp() {
    level++;
    noOfEggsForNextLevel = 4 + (level * 2);  // كل مستوى يحتاج بيض أكثر
    snakeSpeed = 1f + (level/4f);             // زيادة السرعة تدريجياً
    spikeNumber += 1;                         // زيادة عدد الأشواك
}

// نظام النقاط
public void EggEaten(Egg egg) {
    score++;                    // نقطة لكل بيضة
    if (noOfEggsForNextLevel==0) {
        score += 10;            // 10 نقاط إضافية عند إكمال المستوى
    }
}
```

#### **ب) SnakeHead.cs**
**الوظيفة**: التحكم في رأس الثعبان

**الميزات**:
- استقبال أوامر الحركة من Swipe Controls
- إدارة أجزاء جسم الثعبان
- كشف التصادمات مع البيض والعوائق
- نظام الصوت (أصوات الأكل والموت)

**نظام إضافة الأجزاء**:
```csharp
void AddBodyPart() {
    // إضافة جزء جديد خلف الذيل
    // كل بيضة تضيف 5 أجزاء تدريجياً
    partsToAdd = 5;
}
```

#### **ج) SwipeControls.cs**
**الوظيفة**: كشف حركات اللمس (Swipe)

**الآلية**:
```csharp
// دعم اللمس والماوس
- Touch: للهواتف
- Mouse: للاختبار على الكمبيوتر

// أنواع الحركات
public enum SwipeDirection {
    Up, Down, Left, Right
}
```

#### **د) BodyPart.cs**
**الوظيفة**: تمثيل جزء من جسم الثعبان
- تتبع الجزء الذي أمامه
- نظام Memory لحفظ المسار

#### **هـ) Egg.cs**
**الوظيفة**: البيض الذي يأكله الثعبان
- نوعين: عادي وذهبي (آخر بيضة في المستوى)

#### **و) Spike.cs**
**الوظيفة**: الأشواك (العوائق القاتلة)
- تزداد مع كل مستوى

---

## 📱 هيكل المشروع - Flutter

### 1. الملفات الرئيسية (lib/)

#### **أ) main.dart**
**الوظيفة**: نقطة البدء للتطبيق

**الإعدادات**:
```dart
// قفل الاتجاه على Portrait فقط
SystemChrome.setPreferredOrientations([
    DeviceOrientation.portraitUp,
    DeviceOrientation.portraitDown,
]);

// تخصيص شريط الحالة
SystemChrome.setSystemUIOverlayStyle(
    SystemUiOverlayStyle(
        statusBarColor: Colors.transparent,
        statusBarIconBrightness: Brightness.light,
    ),
);

// الثيم
ThemeData(
    brightness: Brightness.dark,
    primarySwatch: Colors.green,
    scaffoldBackgroundColor: Color(0xFF0A0E27),
    colorScheme: ColorScheme.dark(
        primary: Color(0xFF00FF87),     // أخضر نيون
        secondary: Color(0xFF00D9FF),   // أزرق نيون
    ),
)
```

---

### 2. الشاشات (screens/)

#### **أ) splash_screen.dart**
**الوظيفة**: شاشة البداية مع أنيميشن

**الميزات**:
- أنيميشن Scale و Fade للشعار
- أنيميشن Glow متكرر
- جزيئات متحركة في الخلفية
- شريط تحميل متحرك
- انتقال تلقائي بعد 3 ثواني

**الأنيميشنز المستخدمة**:
```dart
// Scale Animation
_scaleAnimation = Tween<double>(begin: 0.5, end: 1.0).animate(
    CurvedAnimation(
        parent: _controller,
        curve: Interval(0.0, 0.6, curve: Curves.elasticOut),
    ),
);

// Glow Animation
_glowAnimation = Tween<double>(begin: 10.0, end: 40.0)
```

#### **ب) home_screen.dart**
**الوظيفة**: الشاشة الرئيسية للعبة

**العناصر**:
- زر Play دائري كبير مع تأثير Pulse
- عنوان اللعبة مع Gradient و Shadow
- 30 جزيء متحرك في الخلفية
- انتقال سلس لشاشة اللعبة

**الأنيميشنز**:
```dart
// Pulse للزر
_pulseAnimation = Tween<double>(begin: 1.0, end: 1.1)

// Float للجزيئات
_floatAnimation = Tween<double>(begin: -10, end: 10)
```

#### **ج) game_screen.dart**
**الوظيفة**: الشاشة الرئيسية للعبة - دمج Unity مع Flutter

**المكونات الرئيسية**:

1. **EmbedUnity Widget**:
```dart
EmbedUnity(onMessageFromUnity: _onUnityMessage)
```
- يعرض محتوى Unity
- يستقبل الرسائل من Unity عبر `onMessageFromUnity`

2. **نظام الرسائل من Unity**:
```dart
void _onUnityMessage(String message) {
    final Map<String, dynamic> data = jsonDecode(message);
    String eventName = data['eventName'];

    // الأحداث المدعومة:
    switch (eventName) {
        case 'OnScoreChanged':   // تغيير النقاط
        case 'OnGameOver':       // انتهاء اللعبة
        case 'OnLevelUp':        // الانتقال لمستوى جديد
        case 'OnGameStarted':    // بدء اللعبة
    }
}
```

3. **إرسال الرسائل لـ Unity**:
```dart
void _sendMessageToUnity(String methodName, String message) {
    sendToUnity('FlutterBridge', methodName, message);
}

// الأوامر المتاحة:
_sendMessageToUnity('StartGame', '');
_sendMessageToUnity('PauseGame', '');
_sendMessageToUnity('ResumeGame', '');
```

4. **إدارة حالة اللعبة**:
- `_isGameStarted`: هل اللعبة بدأت
- `_isGameOver`: هل اللعبة انتهت
- `_isPaused`: هل اللعبة متوقفة
- `_currentScore`: النقاط الحالية
- `_highScore`: أعلى نقاط

5. **التعامل مع دورة حياة التطبيق**:
```dart
@override
void didChangeAppLifecycleState(AppLifecycleState state) {
    switch (state) {
        case AppLifecycleState.paused:   // خروج من التطبيق
            _pauseGame();
        case AppLifecycleState.resumed:  // العودة للتطبيق
            if (!_isGameOver && _isGameStarted) {
                _resumeGame();
            }
    }
}
```

---

### 3. الـ Widgets المخصصة (widgets/)

#### **أ) score_display.dart**
**الوظيفة**: عرض النقاط والمعلومات أثناء اللعب

**العناصر**:
- Score (النقاط الحالية)
- High Score (أعلى نقاط)
- Level (المستوى الحالي)
- زر Pause/Resume
- زر تشغيل/إيقاف الصوت

**التصميم**:
```dart
_InfoCard(
    label: 'SCORE',
    value: score.toString(),
    icon: Icons.stars,
    // مع Gradient و Border و Shadow
)

_ControlIconButton(
    icon: isPaused ? Icons.play_arrow : Icons.pause,
    onPressed: onPauseToggle,
)
```

#### **ب) game_over_dialog.dart**
**الوظيفة**: شاشة Game Over

**الميزات**:
- Blur للخلفية (BackdropFilter)
- عرض النقاط النهائية
- عرض High Score
- شارة "NEW HIGH SCORE!" إذا حقق رقم قياسي
- زر Play Again
- زر Exit

**التأثيرات**:
```dart
// Blur Background
BackdropFilter(
    filter: ImageFilter.blur(sigmaX: 10, sigmaY: 10),
)

// Gradient Dialog
Container(
    decoration: BoxDecoration(
        gradient: LinearGradient(
            colors: [Color(0xFF1A1F3A), Color(0xFF0A0E27)],
        ),
    ),
)
```

---

## 🔗 Unity - Flutter Integration

### 1. كيف تم الدمج؟

#### **الخطوة 1: Export من Unity**
1. فتح Unity Project
2. Build Settings → Android
3. Export Project: ✓
4. Export as Gradle Project
5. النتيجة: مجلد `unityLibrary`

#### **الخطوة 2: دمج unityLibrary في Flutter**
```
android/
├── app/              (Flutter app)
└── unityLibrary/     (Unity exported project)
```

#### **الخطوة 3: إعداد Gradle Files**

**android/settings.gradle.kts**:
```gradle
include ':unityLibrary'
```

**android/app/build.gradle.kts**:
```gradle
dependencies {
    implementation project(':unityLibrary')
}
```

**android/unityLibrary/build.gradle**:
```gradle
android {
    namespace "com.unity3d.player"
    ndkVersion "27.2.12479018"
    compileSdk 36

    ndk {
        abiFilters "armeabi-v7a", "arm64-v8a"
    }
}
```

#### **الخطوة 4: إصلاح مشاكل الـ NDK**

تم إنشاء سكريبت `fix_unity_config.bat` لحل مشاكل:
- تعارض NDK paths
- إعدادات الـ Orientation الخاطئة

**المشكلة**:
```gradle
// Unity يضيف هذا ويسبب مشاكل
ndkPath "C:/Program Files/Unity/..."
```

**الحل**:
```gradle
// حذف ndkPath من build.gradle
// استخدام ndk.dir في local.properties
ndk.dir=D:\\exeMobileAppDev\\Android\\Sdk\\ndk\\27.2.12479018
```

---

### 2. نظام الرسائل (Messaging System)

#### **من Flutter إلى Unity**:
```dart
// في Flutter
import 'package:flutter_embed_unity/flutter_embed_unity.dart';

sendToUnity(
    'FlutterBridge',    // GameObject في Unity
    'StartGame',        // اسم الدالة
    ''                  // البيانات (اختياري)
);
```

#### **من Unity إلى Flutter**:
```csharp
// في Unity - يجب إنشاء GameObject اسمه FlutterBridge
// مع سكريبت يحتوي على:

public void StartGame() {
    // منطق بدء اللعبة
}

public void PauseGame() {
    // منطق إيقاف اللعبة
}

// إرسال رسالة لـ Flutter
string jsonMessage = JsonUtility.ToJson(new {
    eventName = "OnScoreChanged",
    data = JsonUtility.ToJson(new { score = 100 })
});

// الإرسال عبر Bridge
// (يتطلب إعداد FlutterUnityWidget)
```

---

## 🏗️ بناء المشروع (Build Process)

### 1. متطلبات البناء

#### **أدوات مطلوبة**:
- Flutter SDK 3.10.3+
- Android Studio
- Android SDK 36
- Android NDK 27.2.12479018
- JDK 17
- Unity 6000.0 (للتعديل على اللعبة)

### 2. خطوات البناء

#### **للتطوير والاختبار**:
```bash
# 1. تنظيف المشروع
flutter clean

# 2. تحميل الـ packages
flutter pub get

# 3. تشغيل على جهاز/محاكي
flutter run
```

#### **لبناء APK**:
```bash
# بناء APK Debug
flutter build apk --debug

# بناء APK Release
flutter build apk --release

# بناء App Bundle (للنشر على Play Store)
flutter build appbundle --release
```

#### **مكان الملفات الناتجة**:
```
build/app/outputs/
├── flutter-apk/
│   ├── app-debug.apk
│   └── app-release.apk
└── bundle/release/
    └── app-release.aab
```

---

## 🎨 التصميم والألوان

### نظام الألوان المستخدم

```dart
// الألوان الرئيسية
const Color darkBackground = Color(0xFF0A0E27);    // خلفية داكنة
const Color surfaceColor = Color(0xFF1A1F3A);      // لون السطح
const Color primaryNeon = Color(0xFF00FF87);       // أخضر نيون
const Color secondaryNeon = Color(0xFF00D9FF);     // أزرق نيون

// Gradients
LinearGradient(
    colors: [Color(0xFF00FF87), Color(0xFF00D9FF)],
)

// الظلال
BoxShadow(
    color: Color(0xFF00FF87).withOpacity(0.6),
    blurRadius: 40,
    spreadRadius: 10,
)
```

---

## 🐛 المشاكل الشائعة والحلول

### 1. مشكلة NDK Path

**الخطأ**:
```
Android NDK path '.' provided to the build system
Both android.ndkPath and ndk.dir are set
```

**الحل**:
```bash
# تشغيل السكريبت التلقائي
fix_unity_config.bat

# أو يدوياً:
# 1. فتح android/unityLibrary/build.gradle
# 2. حذف أي سطر فيه ndkPath
# 3. التأكد من وجود ndk.dir في local.properties
```

### 2. مشكلة Orientation

**الخطأ**: اللعبة تظهر بشكل أفقي (Landscape)

**الحل**:
```xml
<!-- android/unityLibrary/src/main/AndroidManifest.xml -->
<!-- تغيير من landscape إلى portrait -->
<meta-data
    android:name="unity.player.FreeformWindowOrientation"
    android:value="@string/FreeformWindowOrientation_portrait"
/>
```

### 3. مشكلة Unity لا يظهر

**الأسباب المحتملة**:
1. عدم إضافة `unityLibrary` في `settings.gradle`
2. مشاكل في الـ dependencies
3. نقص ملفات `.aar` في `unityLibrary/libs/`

**الحل**:
```bash
flutter clean
cd android
./gradlew clean
cd ..
flutter pub get
flutter run
```

---

## 📊 أداء المشروع (Performance)

### حجم التطبيق

**APK Release**:
- تقريباً: 80-120 MB
- يتضمن Unity Engine و IL2CPP
- Native Libraries لـ ARM architectures

**التحسينات المطبقة**:
```gradle
// Build only for ARM
ndk {
    abiFilters "armeabi-v7a", "arm64-v8a"
    debugSymbolLevel "none"
}

// ProGuard for code shrinking
buildTypes {
    release {
        minifyEnabled true
        shrinkResources true
    }
}
```

---

## 🎓 الأسئلة المتوقعة من الدكتورة

### 1. "ليه اخترتي Unity مع Flutter؟"

**الإجابة**:
- Unity قوي في الألعاب 2D/3D والفيزياء
- Flutter ممتاز في بناء UI احترافية
- الدمج بينهم يجمع أفضل المزايا:
  - Unity للـ Game Engine
  - Flutter للـ UI/UX والتنقل

### 2. "إزاي Unity بيتواصل مع Flutter؟"

**الإجابة**:
- استخدمنا Package: `flutter_embed_unity`
- Unity يعرض كـ Widget في Flutter
- التواصل عبر نظام Messaging:
  - `sendToUnity()`: من Flutter لـ Unity
  - `onMessageFromUnity`: من Unity لـ Flutter
- البيانات بصيغة JSON

### 3. "إيه الـ Packages اللي استخدمتيها؟"

**الإجابة**:
1. **flutter_embed_unity**: دمج Unity
2. **shared_preferences**: حفظ High Score
3. **flutter_embed_unity_6000_0_android**: دعم Unity 6000
4. **cupertino_icons**: الأيقونات

### 4. "إزاي عملتي الـ Build للـ Android؟"

**الإجابة**:
1. Unity → Export as Gradle Project
2. نسخ `unityLibrary` لمجلد `android/`
3. إعداد `settings.gradle` و `build.gradle`
4. حل مشاكل NDK path
5. `flutter build apk --release`

### 5. "إيه التحديات اللي واجهتيها؟"

**الإجابة**:
1. **مشكلة NDK**: تعارض في paths
   - الحل: إنشاء سكريبت `fix_unity_config.bat`

2. **Orientation خطأ**: اللعبة landscape
   - الحل: تعديل `AndroidManifest.xml`

3. **حجم APK كبير**: 120 MB
   - الحل: تفعيل ProGuard وبناء ARM فقط

### 6. "إيه الـ Architecture المستخدمة؟"

**الإجابة**:
```
┌──────────────────┐
│   Flutter App    │  ← UI/Navigation/State
├──────────────────┤
│  Embed Unity     │  ← Integration Layer
├──────────────────┤
│  Unity Engine    │  ← Game Logic/Physics
├──────────────────┤
│  Native Android  │  ← Platform Layer
└──────────────────┘
```

### 7. "إزاي بتحفظي الـ High Score؟"

**الإجابة**:
```dart
// استخدام SharedPreferences
final prefs = await SharedPreferences.getInstance();

// حفظ
await prefs.setInt('highScore', score);

// قراءة
int highScore = prefs.getInt('highScore') ?? 0;
```

### 8. "إيه الفرق بين Debug و Release Build؟"

**الإجابة**:
- **Debug**:
  - حجم أكبر
  - معلومات debugging
  - أبطأ في الأداء
  - للتطوير والاختبار

- **Release**:
  - حجم أصغر (ProGuard)
  - بدون debugging symbols
  - أداء محسّن
  - للنشر على Play Store

### 9. "إيه الـ Animations المستخدمة؟"

**الإجابة**:
1. **Scale Animation**: تكبير/تصغير
2. **Fade Animation**: ظهور تدريجي
3. **Pulse Animation**: نبض للزر
4. **Float Animation**: حركة الجزيئات
5. **Glow Animation**: توهج متغير

**الـ Curves المستخدمة**:
- `Curves.elasticOut`: للـ bounce effect
- `Curves.easeInOut`: للحركة السلسة
- `Curves.easeIn`: للظهور

### 10. "إيه نظام الـ State Management المستخدم؟"

**الإجابة**:
- استخدمنا **StatefulWidget** مع `setState()`
- بسيط وكافي لحجم المشروع
- لو المشروع أكبر كنا هنستخدم:
  - Provider
  - Riverpod
  - BLoC

---

## 📝 ملخص تقني سريع

### التقنيات:
- Unity 6000.0 (C#)
- Flutter 3.10.3 (Dart)
- Android SDK 36
- NDK 27.2.12479018

### Packages:
- flutter_embed_unity
- shared_preferences
- flutter_embed_unity_6000_0_android

### المشاكل المحلولة:
1. NDK path conflict
2. Orientation issues
3. Unity-Flutter messaging
4. State management
5. Build optimization

### الميزات:
- لعبة Snake كاملة
- نظام نقاط ومستويات
- حفظ High Score
- UI احترافية
- انتقالات سلسة
- أصوات وتأثيرات

---

## 🔧 ملفات مهمة في المشروع

### Flutter Files:
```
lib/
├── main.dart                          # نقطة البدء
├── screens/
│   ├── splash_screen.dart            # شاشة البداية
│   ├── home_screen.dart              # القائمة الرئيسية
│   └── game_screen.dart              # شاشة اللعبة (Unity)
└── widgets/
    ├── score_display.dart            # عرض النقاط
    └── game_over_dialog.dart         # Game Over

pubspec.yaml                           # Dependencies
```

### Unity Files:
```
source_code_unity/Assets/Scripts/
├── GameController.cs                  # المتحكم الرئيسي
├── SnakeHead.cs                       # رأس الثعبان
├── BodyPart.cs                        # أجزاء الجسم
├── SwipeControls.cs                   # التحكم باللمس
├── Egg.cs                             # البيض
└── Spike.cs                           # الأشواك
```

### Android Files:
```
android/
├── app/build.gradle.kts               # Flutter app config
├── unityLibrary/
│   ├── build.gradle                   # Unity library config
│   └── src/main/
│       ├── AndroidManifest.xml        # Permissions & settings
│       └── Il2CppOutputProject/       # Unity compiled code
└── local.properties                   # SDK/NDK paths
```

---

## ✅ Checklist قبل التقديم

- [x] المشروع يعمل بدون أخطاء
- [x] الـ Documentation شامل
- [x] فهم كل الـ Packages المستخدمة
- [x] معرفة كيفية حل المشاكل التقنية
- [x] فهم نظام Unity-Flutter Integration
- [x] القدرة على شرح الـ Architecture
- [x] معرفة الفرق بين Debug و Release
- [x] فهم نظام الـ State Management
- [x] معرفة الـ Build Process
- [x] الاستعداد للأسئلة التقنية

---

## 🎯 نصائح للعرض

### 1. ابدأي بالنظرة العامة
- "المشروع عبارة عن Snake Game بـ Unity مدمج مع Flutter"
- "Unity للـ Game Engine و Flutter للـ UI"

### 2. اعرضي الـ Demo
- شغلي التطبيق على emulator/device
- وريها الـ Splash → Home → Game → Game Over

### 3. اشرحي التقنيات
- Unity: "استخدمته عشان الـ physics و game logic"
- Flutter: "للـ UI الحلو والـ Navigation"

### 4. اذكري التحديات
- "كان فيه مشكلة في NDK path وحليتها بـ..."
- "اللعبة كانت landscape فعدلت الـ manifest"

### 5. اشرحي الكود
- خدي مثال من `game_screen.dart`
- اشرحي الـ messaging system
- ورّيها `sendToUnity()` و `onMessageFromUnity`

### 6. استعدي للأسئلة
- خليكي جاهزة تفتحي أي ملف وتشرحيه
- اعرفي كل package ليه مستخدماه
- فهمي الـ build process

---

## 📞 آخر نصيحة

- **اتكلمي بثقة**: انتي فاهمة المشروع
- **ورّيها الكود**: اشرحي سطر سطر
- **اذكري المصادر**: flutter.dev, unity.com, pub.dev
- **استعدي للـ What If**: "لو عايزة تضيفي multiplayer؟"
  - "ممكن استخدم Firebase Realtime Database"

---

**بالتوفيق! 🚀**

التوثيق ده شامل كل حاجة محتاجها للعرض والمناقشة.
