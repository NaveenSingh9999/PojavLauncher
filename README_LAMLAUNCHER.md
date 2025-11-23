<h1 align="center">🚀 LamLauncher</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Active-success" alt="Status">
  <img src="https://img.shields.io/badge/Platform-Android-green" alt="Platform">
  <img src="https://img.shields.io/badge/License-LGPL--3.0-blue" alt="License">
</p>

<p align="center">
  <em>A modern, optimized Minecraft: Java Edition launcher for Android with stunning UI!</em>
</p>

---

## 🎨 What Makes LamLauncher Special?

**LamLauncher** is a complete redesign of PojavLauncher, focused on delivering:

- **✨ Modern Material Design 3** - Beautiful, smooth UI with contemporary aesthetics
- **🚀 Enhanced Performance** - Optimized rendering pipeline and improved memory management  
- **🎯 Streamlined UX** - Intuitive interface with improved navigation flow
- **🌈 Vibrant Color Scheme** - Eye-pleasing purple & cyan gradient theme
- **⚡ Faster Operations** - Optimized asset loading and intelligent caching
- **📱 Refined Controls** - Improved touch controls with enhanced visual feedback
- **🔧 Better Optimization** - Memory efficient with reduced lag

## 🌟 Core Features

### Runtime Support
- ✅ OpenJDK 8, 17, and 21 for all architectures
- ✅ ARM32, ARM64, x86, and x86_64 support

### Minecraft Versions
- 🎮 Classic versions (rd-132211 onwards)
- 🎮 All releases from 1.0 to 1.21+
- 🎮 Snapshots and Combat Tests
- 🎮 Modded versions (Forge, Fabric, Quilt)

### Graphics & Rendering
- 🖼️ Holy GL4ES (Fast, all versions)
- 🖼️ Zink/Vulkan (Modern, mid-performance)
- 🖼️ LTW OpenGL ES 3 (1.17+ only)
- 🖼️ Custom resolution scaling
- 🖼️ VSync support

### Advanced Features
- 🎮 Custom controls editor
- 🎮 Controller support with remapping
- 🎮 Gyroscope controls
- 📦 Modpack installation (CurseForge)
- 🔧 Multiple Java runtime management
- 💾 Custom game directories
- 🎨 OptiFine & shader support

## 📥 Installation

### Build from Source

1. **Clone the repository:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/LamLauncher.git
   cd LamLauncher
   ```

2. **Update language list:**
   ```bash
   # Linux/macOS
   bash scripts/languagelist_updater.sh
   
   # Windows
   scripts\languagelist_updater.bat
   ```

3. **Build the launcher:**
   ```bash
   ./gradlew :app_lamlauncher:assembleDebug
   ```
   *Use `gradlew.bat` on Windows*

4. **Find your APK:**
   ```
   app_pojavlauncher/build/outputs/apk/debug/app_lamlauncher-debug.apk
   ```

### Advanced Build

For custom builds or development:

1. Download JRE artifacts from [android-openjdk-build-multiarch](https://github.com/PojavLauncherTeam/android-openjdk-build-multiarch/actions)
2. Build GLFW stub: `./gradlew :jre_lwjgl3glfw:build`
3. Build launcher with custom configs

## 🎮 Usage

1. **First Launch:** Grant storage permissions
2. **Add Account:** Microsoft or local account
3. **Select Version:** Choose Minecraft version
4. **Install Mods:** (Optional) Install Forge/Fabric
5. **Play:** Launch and enjoy!

### Performance Tips

- 📊 Allocate appropriate RAM (2-3GB recommended)
- 🎨 Lower render distance on older devices
- ⚙️ Enable sustained performance mode
- 🔄 Use surface rendering for better GPU performance

## 🛠️ Configuration

### Graphics Settings
- Resolution scaler (50%-100%)
- Renderer selection
- VSync toggle
- Sustained performance mode

### Control Customization
- Button size and opacity
- Touch sensitivity
- Gyroscope controls
- Controller mapping

### Java Settings
- Multiple runtime support
- JVM arguments
- Memory allocation
- Sandbox settings

## 🤝 Contributing

We welcome contributions! Here's how you can help:

### Ways to Contribute
- 🐛 **Bug Reports** - Found an issue? Report it!
- ✨ **Feature Requests** - Have an idea? Share it!
- 💻 **Code** - Submit pull requests
- 🌐 **Translations** - Help translate on [Crowdin](https://crowdin.com/project/pojavlauncher)
- 📝 **Documentation** - Improve our docs

### Development Guidelines
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📋 System Requirements

### Minimum
- Android 5.0 (API 21) or higher
- 2GB RAM
- OpenGL ES 2.0 support
- 500MB free storage

### Recommended
- Android 8.0+ (API 26+)
- 4GB+ RAM
- OpenGL ES 3.0 or Vulkan support
- 2GB+ free storage

## 🐛 Known Issues

- Some mods may not work on all devices
- VR mods are not supported
- Performance varies by device

See [issue tracker](https://github.com/YOUR_USERNAME/LamLauncher/issues) for full list.

## 📄 License

LamLauncher is licensed under **GNU Lesser General Public License v3.0**.

See [LICENSE](LICENSE) for details.

## 🙏 Credits & Acknowledgments

### Based On
- **PojavLauncher** - Original launcher foundation
- **PojavLauncher Team** - Core development

### Dependencies
- [Boardwalk](https://github.com/zhuowei/Boardwalk) - JVM Launcher base
- [GL4ES](https://github.com/PojavLauncherTeam/gl4es) - OpenGL ES translation layer
- [OpenJDK](https://github.com/PojavLauncherTeam/openjdk-multiarch-jdk8u) - Java runtime
- [LWJGL3](https://github.com/PojavLauncherTeam/lwjgl3) - Java game library
- [Mesa 3D](https://gitlab.freedesktop.org/mesa/mesa) - Graphics library
- [Zink](https://docs.mesa3d.org/drivers/zink.html) - OpenGL on Vulkan
- And many more open-source projects!

### Special Thanks
- Original PojavLauncher developers
- All contributors and testers
- The Minecraft community

---

## 📞 Support & Community

- 💬 **Discord** - [Join our community](https://discord.com/invite/aenk3EUvER)
- 🐛 **Issues** - [Report bugs](https://github.com/YOUR_USERNAME/LamLauncher/issues)
- 📖 **Wiki** - [Documentation](https://github.com/YOUR_USERNAME/LamLauncher/wiki)

---

<p align="center">
  <strong>Made with ❤️ by the LamLauncher Team</strong><br>
  <em>Bringing modern Minecraft to Android devices</em>
</p>

<p align="center">
  ⭐ Star us on GitHub — it motivates us a lot!
</p>
