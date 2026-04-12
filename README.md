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

---

## 🚀 快速开始（Python 示例）

```python
from kossjs_interface import KossJS

# 创建 JS 运行时实例
with KossJS() as koss:
    # 执行简单表达式
    result = koss.eval("1 + 2")
    print(result)  # 输出: 3

    # 设置全局变量并调用
    koss.set_global("username", "KossJS")
    greeting = koss.eval("'Hello, ' + username")
    print(greeting)  # 输出: Hello, KossJS

    # 使用内置 Fetch API
    koss.eval('''
        fetch("https://api.github.com/users/github")
            .then(res => res.json())
            .then(data => console.log(data.login))
    ''')
```

更多语言示例（C/C++、C#、Java）请查阅 [API 文档](https://github.com/KossJS/KossJS#api-文档)。

---

## 🧭 使用场景

| 场景               | 描述                                                     |
|--------------------|----------------------------------------------------------|
| 🖥️ **桌面软件**    | 脚本插件系统、用户宏、自动化任务                         |
| 🎮 **游戏开发**    | 游戏逻辑脚本、Mod 支持、动态事件                         |
| 🌐 **服务端应用**  | 用户代码沙箱、动态配置、规则引擎                         |
| 📱 **移动端应用**  | Android / HarmonyOS 内嵌脚本执行、动态化功能             |

---

## 📚 资源与文档

- **[官方网站](https://docss-23xr.pages.dev/KossJS/)** - 了解最新动态与博客  
- **[快速开始](https://docss-23xr.pages.dev/KossJS/zh/guide/getting-started.html)** - 分平台安装与基础使用  
- **[API 文档](https://docss-23xr.pages.dev/KossJS/zh/api/API-overview.html)** - 完整函数参考与高级特性  
- **[贡献指南](https://docss-23xr.pages.dev/KossJS/zh/guide/contributing.html)** - 参与项目开发与改进  

---

## 🤝 鸣谢

KossJS 基于以下优秀开源项目构建：

- **[Boa](https://github.com/boa-dev/boa)** - Rust 实现的 ECMAScript 引擎  
- **[Rust](https://www.rust-lang.org/)** - 赋予项目内存安全与性能基石  
- **[ctypes](https://docs.python.org/3/library/ctypes.html)** - Python 与 C 库的无缝互操作  

感谢所有为 KossJS 贡献代码、提交反馈、完善文档的社区成员！  
特别感谢 **[TT23XR Studio](https://github.com/TT23XRStudio)** 的创始与维护工作。

---

## 📄 开源协议

本项目采用 **GNU Affero General Public License v3.0 (AGPL-3.0)** 开源。  
使用前请确保您已理解并同意协议条款。详情请见 [LICENSE](https://github.com/KossJS/KossJS/blob/main/LICENSE) 文件。

---

<p align="center">
  <sub>Built with ❤️ by <a href="https://github.com/sxxyrry">TT23XR Studio</a> and <a href="https://github.com/KossJS/KossJS/graphs/contributors">contributors</a></sub>
</p>
