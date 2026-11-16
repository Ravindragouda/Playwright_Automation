# 🎭 Playwright Automation Guide

Welcome to the Playwright Automation repository! This guide covers what Playwright is, its standout features, how to get started, and the most essential CLI commands you will use daily.

---

## 📖 What is Playwright?

**Playwright** is an open-source end-to-end (E2E) testing and browser automation framework developed and maintained by **Microsoft**. It enables reliable, fast, and capable cross-browser web automation across modern rendering engines—including **Chromium**, **WebKit**, and **Firefox**—using a single, unified API.

Playwright supports multiple programming languages (TypeScript, JavaScript, Python, Java, and .NET) and runs seamlessly on Windows, Linux, and macOS, both locally and in CI/CD pipelines (headless or headed).

---

## ✨ Key Features

* **Cross-Browser & Cross-Platform:** Test across Chromium (Chrome/Edge), WebKit (Safari), and Firefox on Windows, Linux, and macOS, including mobile viewport emulation.
* **Auto-Wait Mechanism:** Playwright automatically waits for elements to be actionable (visible, stable, enabled, and receiving events) before performing actions, eliminating flaky tests and manual `sleep()` calls.
* **Web-First Assertions:** Assertions automatically retry until the expected condition is met or a timeout occurs (e.g., `await expect(locator).toBeVisible()`).
* **Playwright Inspector & Codegen:** Record user interactions directly in the browser to automatically generate test scripts in your preferred language.
* **Trace Viewer:** Capture full execution traces—including DOM snapshots, network requests, console logs, and action timelines—for effortless post-mortem debugging.
* **UI Mode:** An interactive watch-mode interface that lets you explore, run, filter, and time-travel debug tests visually.
* **Network Interception & Mocking:** Intercept, modify, or mock API requests and responses directly within your tests without needing external proxy tools.
* **Parallel Execution & Isolation:** Tests run in isolated **Browser Contexts** (equivalent to brand-new incognito profiles) in milliseconds, enabling high-speed parallel execution with zero shared state.

---

## 🚀 Quick Installation

Ensure you have **Node.js** installed, then initialize a new Playwright project in your terminal:

```bash
# Create a new project directory
mkdir playwright-project && cd playwright-project

# Initialize Playwright
npm init playwright@latest
```

---

## 🛠️ Essential Playwright Commands

Use the following CLI commands to run, record, and debug your tests:

### Running Tests
| Command | Description |
| :--- | :--- |
| `npx playwright test` | Runs all tests across all configured browsers in headless mode. |
| `npx playwright test --headed` | Runs tests in headed mode so you can visually watch the browser. |
| `npx playwright test --ui` | Opens interactive **UI Mode** with watch mode and time-travel debugging. |
| `npx playwright test example.spec.ts` | Runs a specific test file. |
| `npx playwright test -g "login"` | Runs only tests whose titles match the `"login"` pattern. |
| `npx playwright test --project=chromium` | Runs tests exclusively on a specific browser project (e.g., Chromium). |
| `npx playwright test --workers=4` | Runs tests in parallel using a specified number of worker processes. |

### Recording & Debugging
| Command | Description |
| :--- | :--- |
| `npx playwright codegen` | Launches the browser and **Playwright Inspector** to record actions into code. |
| `npx playwright codegen <url>` | Opens a specific URL directly in Codegen (e.g., `npx playwright codegen https://example.com`). |
| `npx playwright test --debug` | Runs tests step-by-step with the Playwright Inspector open. |
| `npx playwright show-trace trace.zip` | Opens the **Trace Viewer** to inspect a saved execution trace file. |

### Reports & Maintenance
| Command | Description |
| :--- | :--- |
| `npx playwright show-report` | Opens the generated HTML test report in your default web browser. |
| `npx playwright install` | Downloads and installs the required Playwright browser binaries. |
| `npx playwright --version` | Displays the currently installed version of Playwright. |
| `npx playwright --help` | Lists all available CLI commands and flags. |

---

## 📂 Default Project Structure

```text
├── tests/                  # Your test specification files (*.spec.ts / *.spec.js)
│   └── example.spec.ts     # Sample test generated during setup
├── playwright.config.ts    # Global configuration (browsers, timeouts, reporters, retries)
├── package.json            # Project dependencies and npm scripts
└── .github/workflows/      # Optional GitHub Actions CI/CD workflow
```