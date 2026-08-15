<p align="center">
  <img src="https://raw.githubusercontent.com/z3n70/Frida-Script-Runner/refs/heads/develop/static/img/fsr_logo.png" width="450">
</p>

# Frida Script Runner

> **Powerful web-based for mobile Android & iOS penetration testing toolkit**

[![Version](https://img.shields.io/badge/version-2.0.0-blue.svg)](https://github.com/z3n70/Frida-Script-Runner)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE) ![platform](https://img.shields.io/badge/OS-osx%2Flinux%2Fwindows-green.svg)
[![Platform](https://img.shields.io/badge/platform-Android%20%7C%20iOS-orange.svg)](https://github.com/z3n70/Frida-Script-Runner) [![python](https://img.shields.io/badge/python-3.x.x-blue.svg?logo=python&labelColor=yellow)](https://www.python.org/downloads/)

**[View Complete Documentation →](http://fsr.pwn.so/index.html)**

---

## Quick Start

Frida Script Runner is a powerful plug & play web-based toolkit designed for Android and iOS penetration testing and mobile application security analysis.
This tool simplifies the process of interacting with Frida by providing a user-friendly Flask-based interface, significantly improving the efficiency of penetration testing workflows.

It features AI-powered script generation through Codex CLI integration with MCP (Model Context Protocol) servers, enabling advanced binary analysis using Ghidra MCP and JADX MCP with minimal manual configuration.

A comprehensive toolkit for analyzing, manipulating, and interacting with mobile applications (Android & iOS), including APK/IPA dumping and automated Frida script generation.

## Tech Graph
<p align="center">
  <img src="https://raw.githubusercontent.com/z3n70/Frida-Script-Runner/refs/heads/main/FSR_Tech_Graph.png" width="800">
</p>

---

## Feature Overview

| Feature Category | Key Features | Status |
|-----------------|--------------|--------|
| **Core Frida** | Script execution, REPL, real-time output, auto-fix | ✅ |
| **AI Generation** | Codex CLI, MCP integration (Ghidra & JADX), prompt engineering | ✅ |
| **Server Management** | Version control, start/stop, auto-detect | ✅ |
| **Frida Gadget Injector** | APK modification, script embedding, multi-arch | ✅ |
| **SSL Detection** | Static analysis, pattern recognition, code preview | ✅ |
| **Mobile Proxy** | HTTP proxy setup, auto IP detection | ✅ |
| **ADB GUI** | Package management, device control, monitoring | ✅ |
| **Codeshare** | Script search, browse, import | ✅ |
| **App Management** | Dump APK/IPA, install, split APK support | ✅ |
| **Device Monitoring** | Real-time status, multi-device support | ✅ |

---
##  Video Tutorials

### FSR - New Version and Other Features
[![Video Thumbnail](https://img.youtube.com/vi/oSC3LPBSi8k/0.jpg)](https://www.youtube.com/watch?v=oSC3LPBSi8k)

### FSR - AI
[![Video Thumbnail](https://img.youtube.com/vi/T0spn-H2qvo/0.jpg)](https://www.youtube.com/watch?v=T0spn-H2qvo)

### Server Manager & Inject Frida Gadget
[![Video Thumbnail](https://img.youtube.com/vi/4I7O6kNDIPk/0.jpg)](https://www.youtube.com/watch?v=4I7O6kNDIPk)

### Android & Custom Script
[![Video Thumbnail](https://img.youtube.com/vi/LGx0L_uQQDY/0.jpg)](https://www.youtube.com/watch?v=LGx0L_uQQDY)

### iOS
[![Video Thumbnail](https://img.youtube.com/vi/kTp5RTjR5uA/0.jpg)](https://www.youtube.com/watch?v=kTp5RTjR5uA)

---

## Prerequisites

### Required Software
- **Python 3.11.x** (required)
- **Flask** (web framework)
- **Frida** (instrumentation toolkit)
- **ADB** (for Android - [installation guide](https://beebom.com/how-to-install-adb-windows-mac/))
- **ideviceinfo** (for iOS - [installation guide](https://command-not-found.com/ideviceinfo))

### AI Features (Optional)
- **Codex CLI** (for AI-powered script generation - [setup guide](https://platform.openai.com/docs/quickstart))
- **Ghidra MCP Server** (for binary analysis integration)
- **JADX MCP Server** (for Android APK analysis)

### Device Requirements
- **Android:** Root access required for Frida server installation
- **iOS:** Jailbroken device with Frida installed via Cydia/Sileo/Zebra

---

## Installation

### Method 1: Native Installation

```bash
1. Clone the repository:
git clone https://github.com/z3n70/Frida-Script-Runner.git
cd Frida-Script-Runner

2. Install Dependencies:
pip3 install -r requirements.txt

3. Run The Application:
python3.11 frida_script.py

4. Access the Web Interface:
http://127.0.0.1:5000
```

### Method 2: Docker Installation

```bash
1. Build and run with Docker Compose:
docker-compose up --build

2. Start Codex Bridge (for AI features):
# On host machine (Windows/Linux/macOS)
python codex-bridge.py

3. Access the Applications:
Frida Script Runner: http://localhost:5000
Codex Bridge Tester: http://localhost:8091
```

### Method 3: Auto Installation

```bash
1. Clone repository
git clone https://github.com/z3n70/Frida-Script-Runner.git
cd Frida-Script-Runner

2. Run Command
chmod +x install.sh

3. And Run
./install.sh
```

---

## AI Setup (Optional)

If you want to use AI-powered script generation:

1. **Install Codex CLI:**
   - Follow the [Codex CLI setup guide](https://platform.openai.com/docs/quickstart)
   - Authenticate with your OpenAI account and ensure the `codex` command is available
2. **Configure MCP Servers (MUST):**
   - Set up Ghidra MCP server for binary analysis
   - Configure JADX MCP server for APK analysis
   - Update paths in `codex-bridge.py` if needed
   - Copy `.config.toml.example` to `.config.toml` and adjust MCP server paths for your setup

---

## Usage

### Basic Usage

1. **Device Setup:**
   - Connect your USB device and run Frida Server (root/jailbreak required)
   - For iPhone: Ensure Frida is installed via Cydia, Sileo, Zebra, or another package manager
2. **Run Scripts:**
   - Open the web interface and select the target package and script
   - Click "Run Frida" to start the Frida process
   - View real-time output in the output container
3. **Script Management:**
   - Android scripts: Place in `Script Directory 1`
   - iOS scripts: Place in `Script Directory 2`
   - See `script.json` for structure and naming conventions

### AI-Powered Script Generation

**Using the Web Interface:**
1. Navigate to the "AI Generate" tab
2. Enter your request (e.g., "Hook the login function and log parameters")
3. Click "Generate Script" to create a custom Frida script

**Using the Codex Bridge Tester:**
1. Access [http://localhost:8091](http://localhost:8091) (when bridge is running)
2. Test different prompts and refine your requests
3. Generated scripts are optimized for ARM Android devices

**Example Prompts:**
- *"Intercept SSL pinning bypass for Android app"*
- *"Hook Java method com.example.App.authenticate and modify return value"*
- *"Monitor file operations and log file paths"*
- *"Hook the main function and log all parameters"*

### Advanced Features

- **Binary Analysis:** AI can access Ghidra/JADX data for accurate function names and addresses
- **Auto-Fix:** Scripts automatically include ARM stability patterns and error handling
- **Real-time Analysis:** MCP servers provide live binary analysis during script generation

---
##  Contributing

Contributions welcome! Please read our [Contributing Guidelines](.github/CONTRIBUTING.md).

1. Fork the repository
2. Create feature branch
3. Test on Android & iOS
4. Submit pull request

**Contact:** [@zenalarifin_](https://x.com/zenalarifin_)

---

##  Contributors

- [Karjok](https://github.com/karjok) - [Yudha](https://github.com/Yudha-ard)
- [Hasyim](https://github.com/xcapri) - [Alfan](https://github.com/alfanilham)
- [Irvan W](https://github.com/IrvanWijayaSardam) - [Yudha](https://github.com/Yudha-ard)
- [Revan](https://github.com/revan-ar) - [Leyoh](https://github.com/leoferaderonugraha)

---

##  Acknowledgments

- **[Frida Project](https://frida.re/)** - Instrumentation toolkit
- **[Frida-ios-dump](https://github.com/AloneMonkey/frida-ios-dump)** - IPA decryption
- **[OpenAI](https://openai.com/)** - Codex-powered generation
- **[Claude](https://claude.ai/)** - Claude is a next generation AI
- **[MCP Servers](https://modelcontextprotocol.io/)** - Binary analysis
- **[GhidraMCP](https://github.com/LaurieWired/GhidraMCP)** - allowing LLMs to autonomously reverse engineer applications.
- **[JadxMCP](https://github.com/zinja-coder/jadx-mcp-server)** - It lets LLMs communicate with the decompiled Android app
- **[Apktool](https://apktool.org/)** - A tool for reverse engineering Android apk files


---

<p align="center">
  <strong>Made with ❤️ <a href="https://secrash.com">Secrash</a> © 2025</strong><br>
</p>
