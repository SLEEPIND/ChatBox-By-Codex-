# 源码修改说明

本文档由 **OpenAI Codex** 生成，用来说明本仓库 Release 中 APK 对 Chatbox Android 版源码做过的主要修改。

## 上游来源

- 上游项目：https://github.com/chatboxai/chatbox
- 当前 APK：chatbox-enter-newline-disable-thinking-button-send-debug.apk
- APK SHA256：$hash
- 包名：xyz.chatboxapp.ce
- 签名：Android debug 签名

## 主要功能改动

### 1. 思考强度选项

Codex 增加了一个通用的「思考强度」设置，支持：

- 未设置：不发送额外思考强度参数，使用模型或服务端默认值。
- 关闭思考：向兼容提供方发送 	hinking.type = disabled。
- 低：low
- 中：medium
- 高：high
- 超高：xhigh

该选项被放到全局设置和每个会话的设置中，并尽量不对模型做白名单检测，方便 DeepSeek、OpenAI-compatible 等兼容接口直接透传。

### 2. 调试日志开关

新增「思考强度调试日志」开关，用于在需要验证请求参数时输出 easoning-effort-debug 日志。

日志只记录与思考强度相关的安全字段，例如：

- 当前选择的思考强度
- 实际请求中的 easoning_effort
- 实际请求中的 	hinking.type

### 3. 输入框发送行为

Codex 修改了输入框键盘行为：

- Enter 只换行，不发送。
- Ctrl+Enter 等 Enter 类快捷发送也被禁用。
- 发送消息只能点击发送按钮。

### 4. Android 兼容性

保留了之前针对 Android 的修正：

- 状态栏 / 安全区边距处理。
- 键盘弹出时输入框区域 resize。
- Capacitor Android 构建配置。

## 主要涉及文件

`	ext
capacitor.config.ts
src/android-edge-to-edge.test.ts
src/renderer/components/InputBox/InputBox.tsx
src/renderer/components/settings/OpenAIReasoningEffortControl.tsx
src/renderer/i18n/locales/en/translation.json
src/renderer/i18n/locales/zh-Hans/translation.json
src/renderer/modals/SessionSettings.tsx
src/renderer/packages/translation.ts
src/renderer/routes/settings/chat.tsx
src/renderer/setup/mobile_safe_area.ts
src/renderer/stores/defaultChatSessionSettings.ts
src/renderer/stores/defaultChatSessionSettings.test.ts
src/renderer/stores/sessionHelpers.ts
src/shared/models/openai-compatible.ts
src/shared/oauth/index.ts
src/shared/providers/definitions/models/chatboxai.ts
src/shared/providers/definitions/models/custom-openai.ts
src/shared/providers/definitions/models/deepseek.ts
src/shared/providers/definitions/models/deepseek.test.ts
src/shared/providers/definitions/models/openai-responses.ts
src/shared/providers/definitions/models/openai-responses.test.ts
src/shared/providers/definitions/models/openai.ts
src/shared/providers/index.ts
src/shared/types/settings.ts
src/shared/types/settings.test.ts
src/shared/utils/input-shortcuts.ts
src/shared/utils/input-shortcuts.test.ts
src/shared/utils/reasoning-effort.ts
src/shared/utils/reasoning-effort.test.ts
`

## 本地验证记录

Codex 构建 APK 前执行过：

`	ext
7 test files passed
26 tests passed
electron-vite Android/mobile build succeeded
Gradle assembleDebug BUILD SUCCESSFUL
apksigner verify succeeded
`

## 使用说明

如果你想复现源码改动，可以参考同目录的：

`	ext
codex-changes.patch
`

该 patch 是为了展示 Codex 本次修改思路和主要文件差异。由于当前工作区不是完整 git clone 状态，patch 可能需要根据你使用的上游 commit 手动调整少量上下文。
