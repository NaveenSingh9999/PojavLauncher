# 🚀 LamLauncher - Build & Optimization Guide

## 📋 Table of Contents
1. [Build Instructions](#build-instructions)
2. [Optimization Tips](#optimization-tips)
3. [Performance Tuning](#performance-tuning)
4. [Troubleshooting](#troubleshooting)
5. [Advanced Configuration](#advanced-configuration)

---

## 🔨 Build Instructions

### Prerequisites
```bash
# Required
- Android SDK (API 21-34)
- JDK 8 or higher
- Git
- Gradle 8.7+

# Optional
- Android Studio
- NDK 25.2.9519653
```

### Quick Build
```bash
# 1. Clone repository
git clone https://github.com/YOUR_USERNAME/LamLauncher.git
cd LamLauncher

# 2. Update language list
bash scripts/languagelist_updater.sh

# 3. Build
./gradlew :app_lamlauncher:assembleDebug

# 4. Output APK
# Location: app_pojavlauncher/build/outputs/apk/debug/
```

### Build Variants
```bash
# Debug (fastest build, larger APK)
./gradlew :app_lamlauncher:assembleDebug

# ProGuard Debug (optimized, debuggable)
./gradlew :app_lamlauncher:assembleProguard

# ProGuard Release (optimized, no debug)
./gradlew :app_lamlauncher:assembleProguardNoDebug

# Release (requires signing)
./gradlew :app_lamlauncher:assembleRelease
```

### Clean Build
```bash
# Clean everything
./gradlew clean

# Clean and rebuild
./gradlew clean :app_lamlauncher:assembleDebug

# Clean specific module
./gradlew :app_lamlauncher:clean
```

---

## ⚡ Optimization Tips

### 1. Memory Optimization

#### Gradle Configuration
```gradle
// In gradle.properties
org.gradle.jvmargs=-Xmx4096M
org.gradle.daemon=true
org.gradle.parallel=true
org.gradle.caching=true
org.gradle.configureondemand=true
```

#### App Memory Settings
- Allocate 2-3GB RAM for Minecraft (mid-range devices)
- Use 1.5-2GB for low-end devices
- 3-4GB for high-end devices
- Monitor heap usage in profiler

### 2. Build Performance

#### Enable Parallel Execution
```bash
./gradlew assembleDebug --parallel --max-workers=4
```

#### Use Build Cache
```bash
./gradlew assembleDebug --build-cache
```

#### Daemon Mode
```bash
./gradlew assembleDebug --daemon
```

### 3. APK Size Optimization

#### Enable ProGuard
```gradle
buildTypes {
    release {
        minifyEnabled true
        shrinkResources true
        proguardFiles getDefaultProguardFile('proguard-android-optimize.txt')
    }
}
```

#### Resource Optimization
```gradle
android {
    defaultConfig {
        vectorDrawables.useSupportLibrary = true
    }
    
    bundle {
        language {
            enableSplit = false
        }
    }
}
```

---

## 🎯 Performance Tuning

### 1. Runtime Performance

#### JVM Arguments (In-Game)
```
# Recommended for 3GB devices
-Xms512M -Xmx2048M -XX:+UseG1GC -XX:+ParallelRefProcEnabled -XX:MaxGCPauseMillis=200

# For 4GB+ devices
-Xms1G -Xmx3G -XX:+UseG1GC -XX:+ParallelRefProcEnabled -XX:MaxGCPauseMillis=200

# For 2GB devices (minimum)
-Xms256M -Xmx1536M -XX:+UseG1GC -XX:MaxGCPauseMillis=200
```

#### Graphics Settings
```
# Best Performance
- Renderer: Holy GL4ES
- Resolution: 70-80%
- Render Distance: 6-8 chunks
- VSync: ON (reduces thermal throttling)

# Balanced
- Renderer: Holy GL4ES or Zink
- Resolution: 90-100%
- Render Distance: 10-12 chunks
- VSync: Optional

# Best Quality
- Renderer: Zink (Vulkan) if supported
- Resolution: 100%
- Render Distance: 14-16 chunks
- VSync: ON
```

### 2. Control Optimization

#### Button Configuration
```xml
<!-- Optimal button sizes -->
Button opacity: 40-60%
Button scale: 100-120%
Touch sensitivity: Medium
Long press delay: 300-500ms
```

#### Performance Mode
```
Settings → Experimental
- Enable sustained performance: ON (for long sessions)
- Use alternate surface: ON (if GPU bound)
- Force big core: ON (if thermal OK)
```

### 3. Storage Optimization

#### Clean Cache Regularly
```bash
# Clear app cache
Settings → Apps → LamLauncher → Clear Cache

# Clear game logs
Delete old latestlog.txt files

# Remove unused JRE versions
Keep only versions you use
```

---

## 🔧 Advanced Configuration

### 1. Custom Renderer Settings

#### GL4ES (Best Compatibility)
```bash
# Environment variables
LIBGL_ES=2
LIBGL_MIPMAP=3
LIBGL_VSYNC=1
LIBGL_USEVBO=1
```

#### Zink (Vulkan)
```bash
# Best for modern devices with Vulkan
Use system Vulkan driver: OFF (use Turnip)
VSync in Zink: ON
```

#### LTW (1.17+ only)
```bash
# For devices with good OpenGL ES 3 support
Render distance limit: 7 chunks (hardware limitation)
Use with Sodium recommended
```

### 2. Control Profiles

#### Create Optimized Profiles
```
1. Gameplay Profile
   - Full controls
   - High opacity buttons
   - Large touch targets

2. Menu Profile
   - Minimal controls
   - Mouse mode default
   - Low opacity

3. Creative Profile
   - Quick block selection
   - Flight controls
   - Inventory shortcuts
```

### 3. Java Runtime Selection

#### Version Matching
```
Minecraft 1.16 and below: Java 8
Minecraft 1.17-1.20.4: Java 17
Minecraft 1.20.5+: Java 21

Forge/Fabric: Check mod loader requirements
OptiFine: Usually Java 8 or 17
```

---

## 🐛 Troubleshooting

### Common Issues

#### 1. Build Failures
```bash
# Problem: Gradle daemon issues
./gradlew --stop
./gradlew clean
./gradlew assembleDebug

# Problem: Missing SDK
# Install Android SDK 34 via SDK Manager

# Problem: NDK not found
# Install NDK 25.2.9519653
```

#### 2. Runtime Crashes
```bash
# Check logs
adb logcat | grep -i lam

# Common fixes
- Reduce memory allocation
- Lower render distance
- Disable resource packs
- Update Java runtime
- Clear app cache
```

#### 3. Performance Issues
```bash
# Diagnostic steps
1. Check device temperature
2. Monitor RAM usage
3. Review CPU usage
4. Check storage space
5. Update graphics drivers

# Quick fixes
- Enable sustained performance
- Lower resolution scaler
- Reduce render distance
- Close background apps
- Enable VSync
```

#### 4. Graphics Issues
```bash
# Renderer problems
- Try different renderer
- Update Mesa/Zink
- Check Vulkan support
- Disable shaders
- Lower graphics settings

# GL4ES specific
- Adjust LIBGL settings
- Check OpenGL ES support
- Update device firmware
```

---

## 📊 Performance Benchmarks

### Expected Performance

#### Low-End Device (2GB RAM, Adreno 505)
```
Minecraft 1.12.2:
- 30-45 FPS
- 6-8 chunk render distance
- 70% resolution scale
- Holy GL4ES renderer

Minecraft 1.20+:
- 20-30 FPS
- 4-6 chunk render distance
- 50-60% resolution scale
- Sodium recommended
```

#### Mid-Range Device (4GB RAM, Adreno 618)
```
Minecraft 1.12.2:
- 50-60 FPS
- 10-12 chunk render distance
- 100% resolution scale
- Holy GL4ES or Zink

Minecraft 1.20+:
- 40-60 FPS
- 8-10 chunk render distance
- 90-100% resolution scale
- Zink recommended
```

#### High-End Device (6GB+ RAM, Adreno 730)
```
Minecraft 1.12.2:
- 60 FPS (VSync)
- 16+ chunk render distance
- 100% resolution scale
- Any renderer

Minecraft 1.20+:
- 60 FPS with Sodium
- 12-16 chunk render distance
- 100% resolution scale
- Zink optimal
```

---

## 🎨 Visual Optimization

### UI Settings
```
# Smooth experience
Button all caps: OFF
Button opacity: 50%
Mouse speed: 1.0-1.2x
Resolution scaler: 90-100%
Ignore notch: ON (if applicable)
```

### Theme Customization
```
# Colors can be customized in
res/values/colors.xml

# Follow the design system
docs/DESIGN_SYSTEM.md
```

---

## 🔐 Security & Privacy

### Sandboxing
```
# .jar execution sandbox
Enable in settings for security
Disable only if trusted mods require it

# Java security manager
Enabled by default
Protects against malicious code
```

### Permissions
```
# Required
- Storage: For game files
- Network: For downloading

# Optional
- Microphone: For voice chat mods
- Notifications: For downloads
```

---

## 📦 Release Preparation

### Before Release
```bash
# 1. Update version
# Edit build.gradle: versionCode & versionName

# 2. Generate changelog
# Update CHANGELOG_LAMLAUNCHER.md

# 3. Test thoroughly
# Different devices, Android versions

# 4. Build release APK
./gradlew assembleRelease

# 5. Sign APK
# Use Android Studio or jarsigner

# 6. Test signed APK
# Install and verify

# 7. Prepare release notes
# Highlight changes and fixes
```

---

## 🌐 Localization

### Update Translations
```bash
# 1. Update language list
bash scripts/languagelist_updater.sh

# 2. Edit strings
# res/values/strings.xml (English base)
# res/values-xx/strings.xml (Other languages)

# 3. Test
# Change device language
# Verify all strings display correctly
```

---

## 📈 Monitoring & Analytics

### Performance Monitoring
```bash
# Use Android Profiler
- CPU usage
- Memory allocation
- Network activity
- Frame rate

# Command line
adb shell dumpsys meminfo net.lamlauncher.app
adb shell dumpsys cpuinfo | grep lamlauncher
```

### Crash Reporting
```bash
# Check crash logs
adb logcat -b crash
adb logcat | grep -i "lamcrashreport"

# App internal logs
# Located in: [Game Directory]/latestcrash.txt
```

---

## 🎯 Best Practices

### Development
1. ✅ Test on multiple devices
2. ✅ Use version control (Git)
3. ✅ Write clean, documented code
4. ✅ Follow design system
5. ✅ Optimize before release

### User Experience
1. ✅ Provide clear error messages
2. ✅ Smooth animations
3. ✅ Responsive UI
4. ✅ Helpful documentation
5. ✅ Regular updates

### Performance
1. ✅ Profile regularly
2. ✅ Optimize hot paths
3. ✅ Minimize memory allocations
4. ✅ Use appropriate data structures
5. ✅ Cache when beneficial

---

## 📞 Support

Need help? Check these resources:

- 📖 **Documentation**: See all .md files in repository
- 💬 **Discord**: [Community Support](https://discord.com/invite/aenk3EUvER)
- 🐛 **Issues**: [GitHub Issues](https://github.com/YOUR_USERNAME/LamLauncher/issues)
- 📧 **Email**: Coming soon

---

<p align="center">
  <strong>Happy Building! 🚀</strong><br>
  <em>LamLauncher - Optimized for Excellence</em>
</p>

---

*Last updated: January 2025*
*Version: 1.0.0*
