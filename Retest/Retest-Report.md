# Retest Report

## Overview

* **Project:** Weather Forecast
* **Retest Date:** 13.09.2026
* **Tester:** Rohachevsk
* **Environment:** Windows 11, Chrome, Production

## Retest Scope

The following previously reported defects were retested after the fixes were implemented:

* BUG-001 — Cyrillic city search
* BUG-002 — Maximum search query length
* BUG-003 — Incorrect localization of buttons 3 and 7
* BUG-004 — Cloudiness, Visibility and UV Index use data from 00:00 instead of the current hour

## Retest Results

| Bug ID  | Description                                                                         | Status   |
| ------- | ----------------------------------------------------------------------------------- | -------- |
| BUG-001 | City search does not work correctly with Cyrillic input                             | **PASS** |
| BUG-002 | Search field accepts more than 50 characters                                        | **PASS** |
| BUG-003 | Buttons 3 and 7 remain in Russian after switching the interface language            | **PASS** |
| BUG-004 | Cloudiness, Visibility and UV Index use data from 00:00 instead of the current hour | **PASS** |

## Detailed Retest Results

### BUG-001 — Cyrillic City Search

**Related Test Case:** TC-011 — Search for a city in different languages

**Expected Result:**
The system should successfully find the existing city and display weather data for Kyiv when `Київ` is entered.

**Actual Result:**
The city `Київ` is found successfully and the weather data is displayed. The previously reported issue could not be reproduced.

**Status:** **PASS**

---

### BUG-002 — Maximum Search Query Length

**Related Test Case:** TC-017 — Maximum Search Query Length

**Expected Result:**
The search field should allow entering a maximum of 50 characters. Characters exceeding the limit should not be accepted.

**Actual Result:**
The search field correctly limits the input to 50 characters. The previously reported issue could not be reproduced.

**Status:** **PASS**

---

### BUG-003 — Incorrect Localization of Buttons 3 and 7

**Related Test Case:** TC-023 — Interface Element Localization

**Expected Result:**
Buttons 3 and 7 should be displayed in the currently selected language.

**Actual Result:**
Buttons 3 and 7 are correctly translated when switching between Russian, English and Ukrainian. The previously reported issue could not be reproduced.

**Status:** **PASS**

---

### BUG-004 — Weather Data Corresponds to the Current Hour

**Related Test Case:** TC-024 — Accuracy: Cloudiness, Visibility and UV Index

**Expected Result:**
Cloudiness, Visibility and UV Index should correspond to the hourly weather data for the current hour.

**Actual Result:**
Cloudiness, Visibility and UV Index now correspond to the appropriate hourly data for the current hour. The previously reported issue could not be reproduced.

**Status:** **PASS**

## Conclusion

All four previously reported defects were retested after the fixes were implemented.

**Retest Result: 4/4 defects passed.**

No previously reported defects were reproduced during retesting.

The fixes were successfully verified, and all four defects are considered **closed**.
