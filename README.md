# ChatBox-By-Codex

这是一个由 **OpenAI Codex** 基于 Chatbox Android 版源码辅助修改、构建并整理发布的非官方调试版 APK。

本仓库主要方便需要的人直接下载测试包。当前版本重点修改了 Android 端输入体验和模型思考强度选项。

## 下载

最新版 APK 请到 Releases 下载：

- [下载 APK](https://github.com/SLEEPIND/ChatBox-By-Codex-/releases/download/v2026.05.14-codex-debug/chatbox-enter-newline-disable-thinking-button-send-debug.apk)
- Release 页面：https://github.com/SLEEPIND/ChatBox-By-Codex-/releases

## 这版改了什么

- 输入框按 Enter 只换行，不再直接发送。
- 禁用 Enter / Ctrl+Enter 等键盘快捷发送，发送只能点击发送按钮。
- 思考强度选项新增「关闭思考」。
- 思考强度保留：未设置、关闭思考、低、中、高、超高。
- 移除了之前容易混淆的「最大」选项。
- 保留思考强度调试日志开关，方便用 db logcat 查看 easoning-effort-debug。
- 继续保留之前对 Android 状态栏、安全区、键盘弹起相关的兼容修正。

## APK 信息

| 项目 | 内容 |
| --- | --- |
| 文件名 | $apkName |
| 大小 | 30.88 MB |
| SHA256 | $hash |
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

- 针对性测试：7 test files / 26 tests passed
- 前端 Android/mobile 构建：通过
- Gradle：ssembleDebug 构建成功
- APK：已通过 pksigner verify --print-certs 校验

## 说明

- 这是非官方调试构建，不代表 Chatbox 官方发布。
- 本仓库 README、发布说明和本次 APK 整理上传均由 **OpenAI Codex** 辅助完成。
- 如果你要继续二次分发或修改，请遵守上游项目的许可证和相关条款。
