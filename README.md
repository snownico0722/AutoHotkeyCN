# AutoHotkeyCN

AutoHotkey v2 的简体中文发行打包仓库。

## 目标

- **AutoHotkey Core 不做魔改**：直接使用官方发布的解释器二进制。
- **AutoHotkeyUX 中文化**：来自 `snownico0722/AutoHotkeyUX`。
- **Ahk2Exe 中文化**：来自 `snownico0722/Ahk2Exe`，在 GitHub Actions 中自举编译。
- **AutoHotkeyCN 只负责总装与发布**：不复制维护上游核心源码。

当前基线：

- AutoHotkey Core：**v2.0.29**
- AutoHotkeyUX：锁定到已审查 commit（见 `versions.json`）
- Ahk2Exe：锁定到已审查 commit（见 `versions.json`）
- Ahk2Exe 上游基线：**v1.1.37.02a2**
- Ahk2Exe 自举 Base：AutoHotkey **v1.1.37.02 U32**

## 构建

打开仓库的 **Actions → Build AutoHotkeyCN → Run workflow**。

工作流会：

1. 下载官方 AutoHotkey v2.0.29 ZIP；
2. 覆盖中文 AutoHotkeyUX；
3. 下载官方 AutoHotkey v1.1.37.02 与 Ahk2Exe v1.1.37.02a2；
4. 用官方 Ahk2Exe 自举编译中文 `Ahk2Exe.exe`；
5. 将中文版编译器装入 `Compiler`；
6. 生成 SHA256；
7. 上传 `AutoHotkey_2.0.29_CN-preview.zip` Artifact。

ZIP 内额外提供 `安装中文版.cmd`，用于直接启动中文安装界面。

> 当前为预览构建。总装使用 commit SHA 锁定中文 UX 与 Ahk2Exe，确保同一版本可重复构建。

## 上游

本项目不是 AutoHotkey 官方中文版本。AutoHotkey、AutoHotkeyUX 与 Ahk2Exe 的版权和许可证归各自上游项目及贡献者所有，详见 [THIRD_PARTY.md](THIRD_PARTY.md)。
