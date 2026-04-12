# KossJS

<p align="center">
  <img src="https://images-sxxyrry.pages.dev/KossJS_Bigger.png" alt="KossJS Logo" width="200"/>
</p>

<p align="center">
  <strong>高性能 · 跨平台 · 嵌入式 JavaScript 运行时引擎</strong>
</p>

<p align="center">
  <a href="https://github.com/KossJS/KossJS/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-AGPL%20v3-blue.svg" alt="License"></a>
  <a href="https://github.com/KossJS/KossJS/releases"><img src="https://img.shields.io/github/v/release/KossJS/KossJS" alt="Release"></a>
  <a href="https://github.com/KossJS/KossJS/actions"><img src="https://img.shields.io/github/actions/workflow/status/KossJS/KossJS/ci.yml" alt="Build Status"></a>
  <img src="https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS%20%7C%20Android%20%7C%20HarmonyOS-blue" alt="Platforms">
  <img src="https://img.shields.io/badge/language-Rust-orange" alt="Language">
</p>

---

## 🚀 简介

**KossJS** 是一个专业级的嵌入式 JavaScript 运行时引擎，使用 **Rust** 语言编写，基于 [Boa](https://github.com/boa-dev/boa) JavaScript 引擎构建。它通过标准的 **C ABI** 向外暴露接口，可被 Python、C/C++、C#、Java/Kotlin 等多种语言无缝调用，为您的应用快速赋予安全、高效的脚本执行能力。

无论是桌面软件的插件系统、游戏脚本引擎，还是服务器端的动态规则配置，KossJS 都能提供极致的性能和可靠的隔离性。

---

## ✨ 核心特性

- **⚡ 高性能与低占用**  
  采用 Rust 实现内存安全和零成本抽象，内存占用仅约 **10-15 MB**，启动迅速，适合嵌入式与资源受限环境。

- **🔌 标准化 C ABI 接口**  
  通过单一动态链接库即可被多种语言调用。官方提供 Python 封装 (`kossjs_interface.py`)，其他语言可通过 P/Invoke、JNA/JNI 等方式轻松集成。

- **🧩 Node.js 兼容模块**  
  内置 **40+** 个常用 Node.js 标准库模块，包括 `fs`、`http`、`crypto`、`path`、`buffer` 等，大量现有脚本可开箱即用。

- **🌐 原生 Fetch API**  
  支持完整的 HTTP/HTTPS 请求，包含 TLS 指纹伪装、自定义请求头与响应处理，无缝对接现代 Web API。

- **📦 完整的 ES Modules 支持**  
  原生支持 `import`/`export` 语法与异步模块加载，拥抱现代 JavaScript 开发标准。

- **🛡️ 实例隔离与安全**  
  每个 `KossInstance` 都是完全隔离的 JS 虚拟机，支持快速创建与销毁，无垃圾回收停顿，适合多租户场景。

---

## 📦 支持的平台

KossJS 为各平台提供原生编译的动态链接库：

| 平台       | 库文件                    | 架构支持              |
|------------|---------------------------|-----------------------|
| Windows    | `kossjs.dll`              | x64                   |
| Linux      | `kossjs.so`               | x64, ARM64            |
| macOS      | `kossjs.dylib`            | x64, ARM64            |
| Android    | `kossjs_android.so`       | x86_64, ARM64, ARMv7  |
| HarmonyOS  | `kossjs_harmony.so`       | x86_64, ARM64         |
