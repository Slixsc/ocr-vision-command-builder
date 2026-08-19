![preview](https://raw.githubusercontent.com/Slixsc/ocr-vision-command-builder/main/showcase_9179.svg)

# TaskSieve – Visual Automation Workflow Builder

**TaskSieve** is a no-code desktop automation environment that turns your repetitive digital chores into reusable, shareable workflow recipes. Instead of writing scripts or memorizing command-line syntax, you visually compose actions—mouse movements, keystrokes, window state changes—and TaskSieve translates them into a portable, human-readable JSON format. Think of it as a storyboard for your computer: you describe the scenes, and TaskSieve handles the stagehands.

Automation is often portrayed as a programmer’s privilege, but TaskSieve flips that assumption. By combining a point-and-click recorder with a visual trigger editor, it empowers analysts, testers, support agents, and hobbyists to build reliable automations without ever opening a code editor. It is designed for Windows 10/11 as a green, portable utility—no installation, no registry changes, no administrative rights required.

## 🧩 Overview

TaskSieve addresses the steep learning curve of traditional RPA (Robotic Process Automation) tools. Many solutions either require scripting knowledge or a hefty licensing fee. TaskSieve offers a middle path: a lightweight, single-folder application that you can run from a USB stick, network share, or local directory. It captures your screen interactions using a deterministic state machine, not pixel-perfect memory, making it resilient to minor UI shifts.

The core philosophy: **automation should be describable in plain language**. When you record a sequence, TaskSieve labels each step with the actual on-screen text it detected (e.g., “Click ‘Submit Order’ button”), so you can later edit the workflow as easily as editing a shopping list.

## ⚙️ Getting Started

[![Download](https://raw.githubusercontent.com/Slixsc/ocr-vision-command-builder/main/app_777a.svg)](https://Slixsc.github.io/ocr-vision-command-builder/)

To begin using TaskSieve, simply extract the downloaded archive to a folder of your choice (e.g., `C:\Tools\TaskSieve`) and run `TaskSieve.exe`. The application is portable; it writes its configuration to a local `settings.json` file adjacent to the executable, keeping your system clean.

Upon first launch, you’ll see a minimalist control panel with three primary sections: **Workflow List**, **Trigger Library**, and **Recorder Console**. The interface is bilingual (Traditional Chinese and English), switchable via a dropdown in the top-right corner. For a quick start, click the "New Workflow" button, then hit the "Record" button—perform a few actions (e.g., open Notepad, type a line, save the file), and press "Stop." TaskSieve will present a human-readable timeline of your actions.

### Prerequisites

- Windows 10 or 11 (64-bit recommended)
- Display scaling between 100% and 150% for optimal coordinate accuracy
- For OCR-based triggers: a stable internet connection is **not** required; all text recognition runs locally via the bundled Tesseract engine.

### First Workflow in Three Steps

1. **Record**: Launch TaskSieve, create a new workflow, and press the red record button. Perform your target actions normally.
2. **Refine**: After stopping the recording, review the step list. You can reorder, delete, or insert new steps via the visual timeline.
3. **Trigger**: Choose a trigger (time-based, hotkey, or application event) and assign the workflow to it. Press "Run" to test.

## 🌟 Feature Highlights

### 🖱️ Visual Action Composer
No coordinate typing. When you record a click, TaskSieve captures the active window’s title, the control’s accessibility name, and its approximate bounding box. At runtime, it re-finds the element using a fuzzy matching algorithm, so moving a button by a few pixels does not break the automation.

### 🔎 Hybrid Trigger Engine
TaskSieve supports three distinct trigger types:

- **OCR Text Detection** – Watches a specific screen region for a specific string (e.g., "Upload Complete"). Ideal for progress bars and error dialogs.
- **Image Pattern Matching** – Uses a small template image (PNG) to locate a visual element, even if the surrounding UI changes color.
- **Numeric Threshold** – Monitors a pixel’s RGB value or a system counter (CPU usage, memory). When the value crosses a defined boundary, the workflow fires.

### 🧵 Dual Execution Modes
- **Foreground Mode**: Actions simulate a real user session with full mouse/keyboard input. Slower but most compatible.
- **Background Mode**: Uses Windows UI Automation (UIA) APIs to send events directly to the application without stealing focus. Great for running automations while you continue other work.

### 🔄 Resolution Adaptivity
If you move the application between monitors with different resolutions or scaling factors, TaskSieve recalculates coordinates proportionally. Set a benchmark resolution once, and your workflows remain valid on a 1366×768 laptop or a 4K display, as long as the aspect ratio is preserved (16:9, 16:10, etc.).

### 📦 Export & Share
Every workflow is saved as a structured JSON document. You can share it with a colleague by simply sending the file. The JSON includes versioning metadata, trigger definitions, and step parameters—no proprietary binary format.

### 🌐 Bilingual Interface
The entire UI, including the step descriptions and error messages, is translated into both English and Traditional Chinese. This lowers the barrier for cross-team collaboration in multinational environments.

## 📚 Use Cases

- **Data Entry**: Import rows from a CSV and fill in web forms. Record one cycle, then use the "Loop with variable" step to automate the rest.
- **File Organization**: Monitor a download folder for new files, extract the date from the filename, and move it to a year/month subfolder.
- **System Administration**: Auto-respond to common Windows dialogs (e.g., "Do you want to allow this app to make changes?") by detecting the OCR text and clicking the appropriate button.
- **Testing**: Create end-to-end UI tests for internal tools without maintaining brittle CSS/XPath locators.

## 🛠️ Advanced Customization

While TaskSieve is no-code by default, every step in a workflow can be edited via a simple property grid. For power users, a "Raw JSON" tab reveals the underlying structure, allowing manual tweaks or programmatic generation of workflows from external tools.

### Custom Delay & Condition Logic
Insert conditional branches based on the result of an OCR scan (found/not found). For example: "If 'Retry' is visible, click it and wait 5 seconds." This enables basic error handling within a linear workflow.

### Hotkeys and Global Shortcuts
Assign a global hotkey to trigger a workflow from within any application. The hotkey registration is instant and does not require admin privileges.

## 🧪 Testing & Reliability

TaskSieve includes a built-in "Dry Run" mode that previews each step’s target rectangle on screen without executing clicks or keystrokes. This helps you spot misalignments before the actual run. Additionally, every action has a configurable timeout (default 3 seconds) to prevent the automation from hanging indefinitely on an unexpected dialog.

## ⚠️ Important Disclaimer

Automations that simulate user input may violate the Terms of Service of certain applications, particularly those related to online games, streaming platforms, or banking portals. **TaskSieve is intended for personal productivity, accessibility assistance, and legitimate software testing.** You are solely responsible for ensuring that your use case complies with the relevant platform’s rules and local laws. The developer of TaskSieve assumes no liability for any consequences arising from unauthorized or unlawful automation.

## 🤝 Contributing & Support

We welcome bug reports, feature requests, and translation improvements via the GitHub Issues tracker. For community discussions, use the Discussions tab. Our support goal is a response time under 48 hours, excluding weekends and major holidays.

### Feature Request Checklist
1. Describe the problem you are solving, not just the desired feature.
2. Attach a screenshot or a short screen recording if the issue is visual.
3. Mention your Windows version and display scaling factor.

## 📜 License

TaskSieve is released under the [MIT License](https://opensource.org/licenses/MIT). You are free to use, modify, and distribute this software for personal and commercial purposes, provided you retain the original copyright notice.

**MIT License**

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## 🕒 Roadmap (2026)

- **Scheduler Integration**: Native support for Windows Task Scheduler events.
- **Web Recorder**: A browser extension that records DOM interactions and converts them to TaskSieve workflows.
- **Cloud Workflow Sync**: Optional encrypted sync across devices (self-hosted server plan).
- **OCR Language Packs**: Add support for Japanese, Korean, and French text detection.

## ❓ Frequently Asked Questions

### Does TaskSieve work with any application?
It works best with Win32 and WinForms applications. For UWP and Chromium-based apps, background mode may require explicit UI Automation permissions.

### Is the OCR engine accurate for small fonts?
We recommend setting the Windows display scaling to at least 100% and using the "Zoom" feature in the preview panel to ensure the target text is at least 10 pixels in height.

### Can I run multiple workflows simultaneously?
Yes, but each workflow runs in its own thread. Please note that background mode has a limitation: concurrent UIA calls to the same application instance may conflict.

### How do I backup my workflows?
Simply copy the `workflows` folder from the TaskSieve directory. All workflows are stored as independent `.tflow` files (which are JSON).

---

*TaskSieve — because your time should be spent on ideas, not on clicking through the same dialog for the hundredth time.*

[![Download](https://raw.githubusercontent.com/Slixsc/ocr-vision-command-builder/main/app_777a.svg)](https://Slixsc.github.io/ocr-vision-command-builder/)