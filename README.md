<p align="center">
  <img src="./doc/images/icon.png" width="144" alt="奶音 Milky Music 图标">
</p>

<h1 align="center">奶音 · Milky Music</h1>

<p align="center"><strong>让音乐、歌词与随身设备连在一起的 Android 音乐播放器</strong></p>

<p align="center">
  <a href="https://github.com/zhzipu/milky-music"><img src="https://img.shields.io/badge/version-1.0.0-4c9f70" alt="Version 1.0.0"></a>
  <a href="./LICENSE"><img src="https://img.shields.io/github/license/zhzipu/milky-music" alt="Apache-2.0 License"></a>
  <a href="https://reactnative.dev/"><img src="https://img.shields.io/badge/React_Native-0.73.11-20232a" alt="React Native 0.73.11"></a>
</p>

奶音（Milky Music）是一款开源 Android 音乐客户端。它把多音源播放、可精细调整的歌词、桌面控制和手表局域网同步放进同一个播放器；界面覆盖手机、横屏、平板与折叠屏。

## 核心亮点

### 专注播放体验的界面

深色外观搭配半透明玻璃质感导航和播放控件。播放页提供歌词、封面和动态音频效果；横屏、平板与折叠屏采用适配的大屏布局。

### 多音源与 B 站音乐

在一个界面中搜索和播放网易云、酷狗及 B 站音频。B 站音源还支持分区排行榜、评论、UP 主作品与合集、收藏和视频详情跳转。各音源的内容和可用性由对应的第三方服务决定。

### 把歌词调到刚刚好

- 自动匹配不合适时，可按歌名和歌手搜索歌词，并为单首歌曲保存匹配结果。
- 可拖动歌词对齐时间，也可分别调整整体偏移和歌词倍速，不改变音频速度。
- 同一条歌词时间轴用于播放器、桌面歌词、小组件和已同步到手表的歌词。

### 手机与 Wear OS 手表直连

配套应用 [LXXWear](https://github.com/zhzipu/LXXWear) 可在同一 Wi-Fi 下获取手机歌单、音频和歌词。选择要同步的歌单与曲目后，手表按需取歌；手机与手表直接通信，不经过云端音乐服务器。

### 主屏幕也能控制音乐

桌面小组件显示专辑封面、歌曲信息、当前歌词、进度和播放控制。提供跟随界面配色、透明、固定深色与固定浅色等样式；桌面歌词也会随播放时间推进。

### 三种听歌识曲引擎

网易云、酷狗与 Shazam 并行识别并合并结果。Shazam 指纹在设备本地计算，网易云 AFP 指纹也在设备上的 WebView 中计算；识曲流程不需要自建服务端。部分识曲请求仍会连接对应的第三方服务。

### 歌单、历史与备份

支持播放历史、相似歌手与歌曲、完整数据备份，以及 OneDrive 远程播放。

## 开始使用

目前仓库提供源码，未附带预编译 APK。构建环境需要 Node.js 18 或更高版本、JDK 17 和 Android SDK。

```bash
npm ci
npm run bundle-android
```

在 Windows PowerShell 中编译：

```powershell
cd android
.\gradlew.bat assembleDebug
```

在 macOS 或 Linux 中编译：

```bash
cd android
./gradlew assembleDebug
```

Debug APK 输出到 `android/app/build/outputs/apk/debug/`。正式构建需要自行配置 Android 签名材料；请勿将密钥或 `keystore.properties` 提交到仓库。正式包名为 `OMG.Milky.Music`，Debug 包名为 `OMG.Milky.Music.dev`。

## 项目来源

本项目基于 [lx-music-mobile](https://github.com/lyswhut/lx-music-mobile) 继续开发，感谢上游作者的开源贡献。完整更新记录见 [CHANGELOG.md](./CHANGELOG.md)，常见问题见 [FAQ.md](./FAQ.md)。

音乐内容由第三方服务提供。使用各音源前，请遵守其服务条款及所在地法律法规。

## 许可证

项目主体采用 [Apache License 2.0](./LICENSE)。`android/app/src/main/assets/afp/` 中的 AFP 指纹实现来自 [ncm-afp](https://github.com/mos9527/ncm-afp)，采用 MIT License。
