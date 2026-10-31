# E2E Framework Boilerplate

> **Modular, Production-Ready End-to-End Testing Engine with Playwright, TypeScript & Page Object Model.**

[![CI Test Suite](https://github.com/marttinroman/e2e-framework-boilerplate/actions/workflows/ci.yml/badge.svg)](https://github.com/marttinroman/e2e-framework-boilerplate/actions)
[![Playwright](https://img.shields.io/badge/Playwright-1.40+-45ba4b?logo=playwright&logoColor=white)](https://playwright.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0+-3178c6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE.md)
[![Author](https://img.shields.io/badge/Author-Marttin%20Roman-0ea5e9)](https://marttinroman.github.io)

---

## 1. Overview & Business Value

In fast-shipping engineering teams, end-to-end testing suites often degrade over time into a slow, brittle bottleneck filled with false positives (*flaky tests*). Developers begin bypassing CI checks, leading to critical regressions in production.

**The Solution:** This boilerplate provides an enterprise-grade starting architecture for Playwright and TypeScript designed around the **KATA Architecture & Page Object Model**:
- **Zero Flakiness:** Dynamic auto-waiting locators and isolated browser contexts.
- **High Throughput:** Multi-browser parallel execution reducing test pipeline runs by up to **75%**.
- **Developer Experience:** Strict TypeScript types, custom test fixtures, and unified Allure reporting.

---

## 2. Layered Architecture (KATA Pattern)

```
TestContext (Layer 1) - Config, Environment variables, Faker utilities
    ↓ extends
UiBase (Layer 2) - Robust Playwright Page wrappers & auto-wait interactions
    ↓ extends
Page Objects (Layer 3) - Atomic Test Components (ATCs) for specific user flows
    ↓ injected into
Test Fixtures (Layer 4) - Dependency injection for isolated test execution
    ↓ executed by
Spec Files (Layer 5) - High-level test scenarios & assertions
```

---

## 3. Tech Stack

- **Runner & Automation:** [Playwright](https://playwright.dev/)
- **Language:** TypeScript 5.x (Strict mode)
- **Runtime & Package Manager:** [Bun](https://bun.sh) / Node.js 18+
- **Reporting:** Allure TestOps & Playwright HTML Report
- **CI/CD:** GitHub Actions (Linux VM matrix)

---

## 4. Quickstart

### Installation

```bash
# Clone the repository
git clone https://github.com/marttinroman/e2e-framework-boilerplate.git
cd e2e-framework-boilerplate

# Install dependencies
bun install   # or npm install

# Install Playwright browser binaries
bunx playwright install --with-deps
```

### Running Tests

```bash
# Run all E2E tests in headless mode
bun run test:e2e

# Run tests in UI mode (interactive debugger)
bunx playwright test --ui

# Run tests on specific browser
bunx playwright test --project=chromium

# Generate and view Allure Report
bun run report:generate
bun run report:open
```

---

## 5. CI/CD Integration

The repository includes a ready-to-use GitHub Actions workflow (`.github/workflows/ci.yml`) that executes on every pull request, running tests in parallel and uploading artifacts on failure (traces, videos, screenshots).

---

## 6. Author & Contact

**Marttin Roman**  
*Senior QA Automation Engineer & SDET*  
- **Portfolio:** [marttinroman.github.io](https://marttinroman.github.io)  
- **LinkedIn:** [linkedin.com/in/marttinroman](https://linkedin.com/in/marttinroman)  
- **Email:** [marttinroman@gmail.com](mailto:marttinroman@gmail.com)  

---

## 7. License

Licensed under the [MIT License](LICENSE.md).
