
# Weather Forecast — Manual QA Testing Portfolio

Welcome to my Manual QA portfolio! This project demonstrates a complete Software Testing Life Cycle (STLC) applied to a real Weather Forecast web application. 

The goal of this project is to showcase my QA workflow: from initial application exploration and test design to execution, defect reporting, and final regression testing. It highlights my ability to write clear documentation, perform root cause analysis using browser tools, and verify bug fixes.

---

## 🎯 Testing Approach & Philosophy

This project strictly focuses on manual testing techniques. The process follows a structured, real-world QA workflow:
**Application Analysis → Scope → Checklist → Test Cases → Execution → Bug Reports → Retest → Regression → Summary**

**Types of Testing Performed:**
* Functional & UI Testing
* Input Validation & Boundary Value Testing
* Localization Testing (Russian / English / Ukrainian)
* Negative Testing
* Data Accuracy Validation (via API network responses)
* Exploratory Testing
* Retesting & Regression Testing

## 💻 Test Environment
* **OS:** Windows 11
* **Browser:** Google Chrome
* **Environment:** Production
* **Tester:** Rohachevsk
* **Initial Execution Date:** 08.09.2026
* **Retest & Regression Date:** 13.09.2026

## 🌦️ Application Under Test (AUT)
The testing scope covered the following features of the Weather Forecast application:
* City search and geolocation
* Current weather information
* Forecasts: Hourly, 3-day, and 7-day
* Weather charts and Radar / Weather map
* Weather metrics: Cloudiness, Visibility, UV Index
* Interface localization and Dark/Light themes
* Favorites functionality and Login interface

---

## 📂 Project Structure & QA Documentation

Use the following links to open each QA artifact:

- [Scope](./Test-Documentation/Scope.md)
- [Checklist](./Test-Documentation/Checklist.md)
- [Test cases](./Test-Documentation/Test-Cases.md)
- [Test execution report](./Test-Documentation/Test-Execution-Report.md)
- [Test summary](./Test-Documentation/Test-Summary.md)
- [Retest report](./Retest/Retest-Report.md)
- [Regression report](./Regression/Regression-Report.md)

### Bug reports

- [BUG-001 — Localized Ukrainian city search](./Bug-Reports/%5BBUG-001%5D%20Cannot%20find%20an%20existing%20city%20using%20the%20localized%20Ukrainian%20name%20%D0%9A%D0%B8%D1%97%D0%B2.md)
- [BUG-002 — Search query length](./Bug-Reports/%5BBUG-002%5D%20Search%20field%20does%20not%20limit%20query%20length%20to%2050%20characters.md)
- [BUG-003 — Language switching](./Bug-Reports/%5BBUG-003%5D%20%E2%80%94%20Buttons%203%20and%207%20remain%20in%20Russian%20after%20changing%20the%20interface%20language.md)
- [BUG-004 — Current-hour weather metrics](./Bug-Reports/%5BBUG-004%5D%20%E2%80%94%20Weather%20data%20shows%2000%3A00%20values.md)

---

## 🐛 Defects Found

During the initial test execution, **4 defects** were identified, documented, and reported.

| Bug ID | Description | Severity | Priority | Related TC |
| --- | --- | --- | --- | --- |
| **[BUG-001](./Bug-Reports/%5BBUG-001%5D%20Cannot%20find%20an%20existing%20city%20using%20the%20localized%20Ukrainian%20name%20%D0%9A%D0%B8%D1%97%D0%B2.md)** | **Cyrillic City Search:** App failed to find existing cities using Cyrillic (e.g., "Київ"). Latin versions worked correctly. | High | High | TC-011 |
| **[BUG-002](./Bug-Reports/%5BBUG-002%5D%20Search%20field%20does%20not%20limit%20query%20length%20to%2050%20characters.md)** | **Maximum Search Query Length:** Search field accepted ~1000 characters instead of the expected 50-character limit. | Medium | Medium | TC-017 |
| **[BUG-003](./Bug-Reports/%5BBUG-003%5D%20%E2%80%94%20Buttons%203%20and%207%20remain%20in%20Russian%20after%20changing%20the%20interface%20language.md)** | **Incorrect Localization:** Buttons 3 and 7 remained in Russian when switching interface languages. | Minor | Medium | TC-023 |
| **[BUG-004](./Bug-Reports/%5BBUG-004%5D%20%E2%80%94%20Weather%20data%20shows%2000%3A00%20values.md)** | **Incorrect Weather Data for Current Hour:** Cloudiness, Visibility, and UV Index displayed midnight (00:00) data instead of current hour data. | Major | High | TC-024 |

### 🔍 Highlight: Deep Defect Investigation (BUG-004)

To ensure the defect was accurately reported, I didn't just log a UI mismatch. I used **Chrome DevTools (Network tab)** to inspect the `Open-Meteo API` response. I discovered that while the API provided a specific current time (e.g., `2026-09-09T09:15`) and corresponding hourly data (`09:00`, `10:00`), the application was failing to map the exact time. As a fallback, the frontend defaulted to index `0` of the array, incorrectly rendering the `00:00` data for the user.

---

## 🔄 Retest & Regression Testing

Following the implementation of bug fixes, a dedicated testing cycle was performed on **13.09.2026**.

### Retest Results

All four reported defects were successfully retested. No previous defects were reproduced.

| Bug ID | Issue Verified | Retest Status |
| --- | --- | --- |
| BUG-001 | Cyrillic search functions correctly | ✅ **PASS** |
| BUG-002 | Search input strictly limited to 50 characters | ✅ **PASS** |
| BUG-003 | Buttons 3 and 7 localize correctly | ✅ **PASS** |
| BUG-004 | Weather metrics match the current hour data | ✅ **PASS** |

### Regression Testing

A targeted regression run was executed to ensure that the bug fixes did not negatively impact existing functionality. The regression scope covered city search, validation, weather accuracy, and localization.

* **Selected Regression Test Cases:** `TC-001`, `TC-003`, `TC-006`, `TC-008`, `TC-009`, `TC-011`, `TC-017`, `TC-020`, `TC-023`, `TC-024`
* **Regression Result:** **10/10 PASS**.
* **Conclusion:** The implemented fixes were stable and caused no regressions in the application.

---

## 🛠️ Tools Used

* **Google Chrome & Chrome DevTools** (Network monitoring, API response validation)
* **Open-Meteo API** (Data validation)
* **GitHub** (Version control, Repository hosting)
* **Markdown** (Test documentation formatting)

---

*Thank you for reviewing my portfolio project! This repository demonstrates my ability to design comprehensive tests, investigate bugs deeply, and maintain clear, professional QA documentation.*

