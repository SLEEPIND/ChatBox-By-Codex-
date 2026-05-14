# ChatBox-By-Codex

这是一个由 **OpenAI Codex** 基于 Chatbox Android 版源码辅助修改、构建并整理发布的非官方调试版 APK。

本仓库主要方便需要的人直接下载测试包。当前版本重点修改了 Android 端输入体验和模型思考强度选项。

## 下载

最新版 APK 请到 Releases 下载：

- [下载 APK](https://github.com/SLEEPIND/ChatBox-By-Codex-/releases/download/v2026.05.14-codex-debug/chatbox-enter-newline-disable-thinking-button-send-debug.apk)
- Release 页面：https://github.com/SLEEPIND/ChatBox-By-Codex-/releases

## 这版改了什么

- 思考强度选项新增「关闭思考」。
- 思考强度保留：未设置、关闭思考、低、中、高、超高。
- 保留思考强度调试日志开关，方便用adb logcat 查看reasoning-effort-debug。

## APK 信息

| 项目 | 内容 |
| --- | --- |
| 文件名 | chatbox-enter-newline-disable-thinking-button-send-debug.apk |
| 大小 | 30.88 MB |
| SHA256 | 95ABF9C8A4EDE6ABACFD9FA5DC27B8334C6652D51AB611C9513872188D4CFF23 |
| 包名 | xyz.chatboxapp.ce |
| 应用名 | Chatbox |
| 签名 | Android debug 签名 |

## 安装方法

`powershell
adb install -r .\chatbox-enter-newline-disable-thinking-button-send-debug.apk
`

如果手机上已有不同签名版本，可能需要先卸载旧版再安装。

## 验证记录

Codex 在本地完成了以下验证：

- 针对性测试:7 test files / 26 tests passed
- 前端 Android/mobile 构建:通过
- Gradle:ssembleDebug 构建成功
- APK:已通过pksigner verify --print-certs 校验

## 说明

- 这是非官方调试构建，不代表 Chatbox 官方发布。
- 本仓库 README、发布说明和本次 APK 整理上传均由 **OpenAI Codex** 辅助完成。
- 如果你要继续二次分发或修改，请遵守上游项目的许可证和相关条款。
