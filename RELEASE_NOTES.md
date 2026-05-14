# v2026.05.14-codex-debug

由 **OpenAI Codex** 整理发布的 Chatbox Android 非官方调试 APK。

## 更新内容

- Enter 改为只换行，不发送。
- 禁用键盘快捷发送；发送只能点击发送按钮。
- 思考强度增加「关闭思考」。
- 思考强度选项为：未设置、关闭思考、低、中、高、超高。
- 移除「最大」选项。
- 保留思考强度调试日志开关。

## APK

- 文件名：$apkName
- 大小：30.88 MB
- SHA256：$hash

## 安装

`powershell
adb install -r .\chatbox-enter-newline-disable-thinking-button-send-debug.apk
`

> 这是 debug 签名的非官方测试包。
