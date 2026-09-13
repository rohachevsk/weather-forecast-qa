
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

All QA documentation is organized logically to reflect a professional testing environment. 

```text
Weather-Forecast-QA/
├── README.md
├── Test-Documentation/
│   ├── [Scope.md](./Test-Documentation/Scope.md)
│   ├── [Checklist.md](./Test-Documentation/Checklist.md)
│   ├── [Test-Cases.md](./Test-Documentation/Test-Cases.md)
│   ├── [Test-Execution-Report.md](./Test-Documentation/Test-Execution-Report.md)
│   └── [Test-Summary.md](./Test-Documentation/Test-Summary.md)
│
├── Bug-Reports/
│   ├── [BUG-001.md](./Bug-Reports/BUG-001.md)
│   ├── [BUG-002.md](./Bug-Reports/BUG-002.md)
│   ├── [BUG-003.md](./Bug-Reports/BUG-003.md)
│   └── [BUG-004.md](./Bug-Reports/BUG-004.md)
│
├── Retest/
│   ├── [Retest-Report.md](./Retest/Retest-Report.md)
│   └── Screenshots/
│       ├── BUG-001-retest.png
│       ├── BUG-002-retest.png
│       ├── BUG-003-retest-01.png
│       ├── BUG-003-retest-02.png
│       ├── BUG-003-retest-03.png
│       ├── BUG-004-retest-01.png
│       ├── BUG-004-retest-02.png
│       └── BUG-004-retest-03.png
└── Regression/
    └── [Regression-Report.md](./Regression/Regression-Report.md)

```

---

## 🐛 Defects Found

During the initial test execution, **4 defects** were identified, documented, and reported.

| Bug ID | Description | Severity | Priority | Related TC |
| --- | --- | --- | --- | --- |
| **[BUG-001](https://www.google.com/search?q=./Bug-Reports/BUG-001.md)** | **Cyrillic City Search:** App failed to find existing cities using Cyrillic (e.g., "Київ"). Latin versions worked correctly. | High | High | TC-011 |
| **[BUG-002](https://www.google.com/search?q=./Bug-Reports/BUG-002.md)** | **Maximum Search Query Length:** Search field accepted ~1000 characters instead of the expected 50-character limit. | Medium | Medium | TC-017 |
| **[BUG-003](https://www.google.com/search?q=./Bug-Reports/BUG-003.md)** | **Incorrect Localization:** Buttons 3 and 7 remained in Russian when switching interface languages. | Minor | Medium | TC-023 |
| **[BUG-004](https://www.google.com/search?q=./Bug-Reports/BUG-004.md)** | **Incorrect Weather Data for Current Hour:** Cloudiness, Visibility, and UV Index displayed midnight (00:00) data instead of current hour data. | Major | High | TC-024 |

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

