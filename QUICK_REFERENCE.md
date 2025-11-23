# 📌 LamLauncher Quick Reference Card

## 🚀 Quick Start

### Build Commands
```bash
# Debug Build
./gradlew :app_lamlauncher:assembleDebug

# Release Build
./gradlew :app_lamlauncher:assembleRelease

# Clean Build
./gradlew clean assembleDebug
```

### APK Location
```
app_pojavlauncher/build/outputs/apk/debug/app_lamlauncher-debug.apk
```

---

## 🎨 Design System

### Colors
| Name | Hex | Usage |
|------|-----|-------|
| Primary | `#6C63FF` | Buttons, highlights |
| Accent | `#00D9FF` | Actions, links |
| Background | `#0F0F14` | Main background |
| Card | `#1A1A24` | Cards, panels |
| Text Primary | `#FFFFFF` | Main text |
| Text Secondary | `#9FA2B4` | Secondary text |

### Spacing (4dp base)
- Tiny: 4dp
- Small: 8dp
- Medium: 16dp
- Large: 24dp
- XLarge: 32dp

---

## ⚡ Performance

### JVM Args (3GB Device)
```
-Xms512M -Xmx2048M -XX:+UseG1GC
```

### Optimal Settings
- RAM: 2-3GB
- Resolution: 80-100%
- Render: 8-12 chunks
- VSync: ON

---

## 🔧 Key Files

### Core
- `LamApplication.java` - Main app
- `AndroidManifest.xml` - App config
- `build.gradle` - Build config
- `strings.xml` - App strings
- `colors.xml` - Color scheme
- `styles.xml` - Theme

### Documentation
- `README_LAMLAUNCHER.md` - Main docs
- `LAMLAUNCHER_CHANGES.md` - Changes
- `CHANGELOG_LAMLAUNCHER.md` - Versions
- `DESIGN_SYSTEM.md` - UI guide
- `BUILD_OPTIMIZATION_GUIDE.md` - Build tips

---

## 📦 Package Info

### Old → New
```
Package: net.kdt.pojavlaunch → net.lamlauncher.app
App ID:  net.kdt.pojavlaunch → net.lamlauncher.app
Class:   PojavApplication → LamApplication
Module:  app_pojavlauncher → app_lamlauncher
```

---

## 🐛 Troubleshooting

### Build Issues
```bash
./gradlew --stop
./gradlew clean
bash scripts/languagelist_updater.sh
./gradlew assembleDebug
```

### Runtime Issues
1. Check RAM allocation
2. Lower render distance
3. Change renderer
4. Clear cache
5. Update JRE

---

## 📊 Version Requirements

### Minimum
- Android: 5.0 (API 21)
- RAM: 2GB
- Storage: 500MB

### Recommended
- Android: 8.0+
- RAM: 4GB+
- Storage: 2GB+

---

## 🎮 Renderer Guide

| Renderer | Best For | Notes |
|----------|----------|-------|
| GL4ES | All versions | Fast, compatible |
| Zink | Modern devices | Vulkan required |
| LTW | 1.17+ | 7 chunk limit |

---

## 📞 Quick Links

- 💬 Discord: discord.com/invite/aenk3EUvER
- 🐛 Issues: GitHub Issues
- 📖 Wiki: GitHub Wiki
- 📚 Docs: See .md files

---

## ✅ Checklist

### Before Building
- [ ] Clone repository
- [ ] Update language list
- [ ] Check SDK installed
- [ ] Review build variant

### Before Release
- [ ] Update version
- [ ] Test on devices
- [ ] Update changelog
- [ ] Build release APK
- [ ] Sign APK
- [ ] Prepare notes

### After Install
- [ ] Grant permissions
- [ ] Add account
- [ ] Select version
- [ ] Configure settings
- [ ] Test gameplay

---

## 🎯 Quick Tips

### Performance
- Use G1GC garbage collector
- Enable sustained performance
- Lower resolution if needed
- Monitor temperature

### Controls
- Customize button size
- Adjust opacity
- Set mouse speed
- Configure sensitivity

### Graphics
- Match renderer to device
- Adjust render distance
- Enable VSync
- Use resolution scaler

---

<p align="center">
  <strong>LamLauncher v1.0.0</strong><br>
  <em>Quick Reference Card</em>
</p>

---

*Print and keep handy! 📋*
