<H1 align="center">MidnightLauncher</H1>

<img src="https://github.com/MidnightLauncher/MidnightLauncher/blob/readme-update/app_pojavlauncher/src/main/assets/midnightlauncher.png" align="left" width="150" height="150" alt="MidnightLauncher logo">

* MidnightLauncher is a [PojavLauncher](https://github.com/PojavLauncherTeam/PojavLauncher) fork focused on customizability and performance.

* It is a launcher that allows you to play Minecraft: Java Edition on your Android device!

* It can run almost every version of Minecraft, allowing you to use .jar only installers to install modloaders such as [Forge](https://files.minecraftforge.net/) and [Fabric](http://fabricmc.net/), mods like [OptiFine](https://optifine.net) and [LabyMod](https://www.labymod.net/en), as well as (though discouraged) hack clients like [Wurst](https://www.wurstclient.net/), and much more!

* For more details [check out PojavLauncher wiki](https://pojavlauncherteam.github.io/)

## Navigation
- [Introduction](#introduction)  
- [Getting MidnightLauncher](#getting-midnightlauncher)
- [Building](#building) 
- [Current status](#current-status) 
- [License](#license) 
- [Contributing](#contributing) 
- [Credits & Third party components and their licenses](#credits--third-party-components-and-their-licenses-if-available)

## Introduction 
* MidnightLauncher is a Minecraft: Java Edition launcher for Android based on [PojavLauncher](https://github.com/PojavLauncherTeam/PojavLauncher). 
* This launcher can launch almost all available Minecraft versions ranging from rd-132211 to 1.21 snapshots (including Combat Test versions). 
* Modding via Forge and Fabric are also supported. 
* This repository contains source code for Android. 
* Because this is a mainly Android fork, for iOS/iPadOS, check out [PojavLauncher_iOS](https://github.com/PojavLauncherTeam/PojavLauncher_iOS).

## Getting MidnightLauncher

You can get MidnightLauncher via two methods:

1. You can get the prebuilt app from [stable releases](https://github.com/MidnightLauncher/MidnightLauncher/releases) or [automatic builds](https://github.com/MidnightLauncherTeam/MidnightLauncher/actions).

2. You can [build](#building) from source.
## Building
If you want to build from source code, follow the steps below.
Most steps require getting files from the PojavLauncher repositories, keep that in mind.
### Java Runtime Environment (JRE)
- JRE for Android is [here](https://github.com/PojavLauncherTeam/openjdk-multiarch-jdk8u), and the build script is [here](https://github.com/PojavLauncherTeam/android-openjdk-build-multiarch).
- Follow build instruction on build script [README.md](https://github.com/PojavLauncherTeam/android-openjdk-build-multiarch/blob/buildjre8/README.md).
- You can also get [CI auto builds](https://github.com/PojavLauncherTeam/android-openjdk-build-multiarch/actions) if you are lazy or are failing to build it for some reason.
* Either get the `jre8-pojav` artifact from auto builds, or split all artifacts by yourself:</br>
   - Get JREs for all of 4 supported architectures (arm, arm64, x86, x86_64) </br> 
      - Split JRE into parts:</br>
                Platform-independent: .jar files, libraries, configs, etc...</br>
                Platform-dependent: .so files, etc...</br>
        - Create:</br>
                A file named `universal.tar.xz` with all platform-independent files</br>
                4 files named `bin-<arch>.tar.xz` with all platform-dependent files per-architecture</br>
        - Put these in the `assets/components/jre/` folder</br>
        - (If needed) update the Version file with the current date</br>

### LWJGL
The build instructions for the custom LWJGL are available over the [LWJGL repository](https://github.com/PojavLauncherTeam/lwjgl3)

### The Launcher
- Because languages are auto-added by Crowdin, you need to run the language list generator before building. In the project directory, run:

* On Linux, Mac OS:
```
chmod +x scripts/languagelist_updater.sh
bash scripts/languagelist_updater.sh
```
* On Windows:
```
scripts\languagelist_updater.bat
```
Then, run these commands ~~or build using Android Studio~~.

* Build GLFW stub:
```
./gradlew :jre_lwjgl3glfw:build
```       
* Build the launcher
```
./gradlew :app_pojavlauncher:assembleDebug
```
(Replace `gradlew` with `gradlew.bat` if you are building on Windows).

## Current status
- [ ] New themes/custom themes and such
- [ ] Material you support (partially done) 
- [x] Little performance boost (by setting the nice value of the game process to -20)

## Known Issues
- All the issues from [PojavLauncher](https://github.com/PojavLauncherTeam/PojavLauncher?tab=readme-ov-file#known-issues).
## License
- MidnightLauncher is licensed under [GNU GPLv3](https://github.com/MidnightLauncher/MidnightLauncher/blob/master/LICENSE).

## Contributing
Contributions are welcome! We welcome any type of contribution, not only code. For example, you can help the wiki shape up.

Any code change to this repository should be submitted as a pull request. The description should explain what the code does and give steps to execute it.

## Credits & Third party components and their licenses (if available)
- [PojavLauncher](https://github.com/PojavLauncherTeam/PojavLauncher) for source code.
- [Boardwalk](https://github.com/zhuowei/Boardwalk) (JVM Launcher): Unknown License/[Apache License 2.0](https://github.com/zhuowei/Boardwalk/blob/master/LICENSE) or GNU GPLv2.
- Android Support Libraries: [Apache License 2.0](https://android.googlesource.com/platform/prebuilts/maven_repo/android/+/master/NOTICE.txt).
- [GL4ES](https://github.com/PojavLauncherTeam/gl4es): [MIT License](https://github.com/ptitSeb/gl4es/blob/master/LICENSE).<br>
- [OpenJDK](https://github.com/PojavLauncherTeam/openjdk-multiarch-jdk8u): [GNU GPLv2 License](https://openjdk.java.net/legal/gplv2+ce.html).<br>
- [LWJGL3](https://github.com/PojavLauncherTeam/lwjgl3): [BSD-3 License](https://github.com/LWJGL/lwjgl3/blob/master/LICENSE.md).
- [LWJGLX](https://github.com/PojavLauncherTeam/lwjglx) (LWJGL2 API compatibility layer for LWJGL3): unknown license.<br>
- [Mesa 3D Graphics Library](https://gitlab.freedesktop.org/mesa/mesa): [MIT License](https://docs.mesa3d.org/license.html).
- [pro-grade](https://github.com/pro-grade/pro-grade) (Java sandboxing security manager): [Apache License 2.0](https://github.com/pro-grade/pro-grade/blob/master/LICENSE.txt).
- [bhook](https://github.com/bytedance/bhook) (Used for exit code trapping): [MIT license](https://github.com/bytedance/bhook/blob/main/LICENSE).
- [libepoxy](https://github.com/anholt/libepoxy): [MIT License](https://github.com/anholt/libepoxy/blob/master/COPYING).
- [virglrenderer](https://github.com/PojavLauncherTeam/virglrenderer): [MIT License](https://gitlab.freedesktop.org/virgl/virglrenderer/-/blob/master/COPYING).
- Thanks to [MCHeads](https://mc-heads.net) for providing Minecraft avatars.
