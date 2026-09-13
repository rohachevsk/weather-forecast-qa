# 📋 Test Execution Report — Weather Forecast

**Module:** City Search
**Product:** Weather Forecast
**Test Date:** 08.09.2026
**Tester:** Rohachevsk
**Environment:** Windows 11, Chrome, Production
**Test Scope:** City Search and related weather data validation

---

# 🎯 Test Objective

The purpose of this test execution was to verify the City Search functionality and related weather data displayed by the application.

The following areas were covered:

* Valid and invalid city search
* Partial city names
* Case sensitivity
* Cyrillic and Latin characters
* Mixed character input
* Special characters, digits and emoji
* Leading/trailing spaces
* Empty and whitespace-only input
* Minimum and maximum search query length
* Error handling
* Previous city state after a failed search
* Display of the selected city and weather data
* Interface localization
* Accuracy of selected weather data

Testing was performed based on the test cases documented in `Test-Documentation/Test-Cases.md`.

Open-Meteo data was additionally used as a reference when validating weather data accuracy.

---

# 📊 Test Execution Summary

| Metric                        | Result |
| ----------------------------- | -----: |
| Total Test Cases              |     24 |
| Passed                        |     20 |
| Failed                        |      4 |
| Partial / Needs Clarification |      0 |
| Blocked                       |      0 |
| Confirmed Bugs                |      4 |
| Pass Rate                     |  83.3% |

---

# 🧪 Test Case Results

| Test Case | Description                                       | Type          | Result | Notes                                                               |
| --------- | ------------------------------------------------- | ------------- | ------ | ------------------------------------------------------------------- |
| TC-001    | Search for a valid city                           | Positive      | ✅ PASS | Kyiv found successfully                                             |
| TC-002    | Search for a non-existent city                    | Negative      | ✅ PASS | `City not found` notification displayed                             |
| TC-003    | Search for a multi-word city                      | Positive      | ✅ PASS | New York found successfully                                         |
| TC-004    | Search using a partial city name via autocomplete | Positive      | ✅ PASS | City found after selecting an autocomplete suggestion               |
| TC-005    | Case-insensitive city search                      | Positive      | ✅ PASS | Kyiv found with mixed letter case                                   |
| TC-006    | Search with an empty query                        | Negative      | ✅ PASS | No search performed; application remains stable                     |
| TC-007    | Search using special characters                   | Negative      | ✅ PASS | Application handles input without breaking                          |
| TC-008    | Search with leading and trailing spaces           | Positive      | ✅ PASS | Kyiv found successfully                                             |
| TC-009    | Search with a typo                                | Negative      | ✅ PASS | `City not found` notification displayed                             |
| TC-010    | Search using the wrong keyboard layout            | Negative      | ✅ PASS | `City not found` notification displayed                             |
| TC-011    | Search using a localized city name                | Positive      | ❌ FAIL | `Київ` is not found — BUG-001                                       |
| TC-012    | Search using mixed Latin and Cyrillic characters  | Negative      | ✅ PASS | Application remains stable                                          |
| TC-013    | Search using digits                               | Negative      | ✅ PASS | `City not found` notification displayed                             |
| TC-014    | Search using emoji                                | Negative      | ✅ PASS | Application handles input without breaking                          |
| TC-015    | Search using spaces only                          | Negative      | ✅ PASS | No search performed; application remains stable                     |
| TC-016    | Minimum search query length                       | Boundary      | ✅ PASS | Search behavior corresponds to the defined input conditions         |
| TC-017    | Maximum search query length                       | Boundary      | ❌ FAIL | Search field accepts more than 50 characters — BUG-002              |
| TC-018    | Display of the selected city and weather data     | UI            | ✅ PASS | City and weather information displayed correctly                    |
| TC-019    | Weather data corresponds to the selected city     | Functional    | ✅ PASS | Weather data corresponds to the selected city                       |
| TC-020    | `City not found` notification                     | UI / Negative | ✅ PASS | Notification displayed correctly                                    |
| TC-021    | Previous city remains after a failed search       | Functional    | ✅ PASS | Previous weather data remains displayed                             |
| TC-022    | Search for a partial city name using Enter        | Positive      | ✅ PASS | Partial city name successfully processed                            |
| TC-023    | Interface localization                            | Localization  | ❌ FAIL | Buttons 3 and 7 remain in Russian — BUG-003                         |
| TC-024 | Accuracy of current weather data | Data Accuracy | ❌ FAIL | [BUG-004](../Bug-Reports/BUG-004%20%E2%80%94%20Weather%20data%20shows%2000%3A00%20values.md) |

---

# 🔍 Detailed Test Case Results

## TC-001 — Search for a valid city

**Test Data:** `Kyiv`

**Result:** ✅ PASS

The system successfully finds Kyiv and displays the corresponding weather information.

---

## TC-002 — Search for a non-existent city

**Test Data:** `Xyzqwerty123`

**Result:** ✅ PASS

The system does not return a city and displays the `City not found` notification.

---

## TC-003 — Search for a multi-word city

**Test Data:** `New York`

**Result:** ✅ PASS

The system successfully finds New York and displays the corresponding weather information.

---

## TC-004 — Search using a partial city name via autocomplete

**Test Data:** `Kyi`

**Result:** ✅ PASS

The system displays autocomplete suggestions. Selecting the corresponding city from the list successfully performs the search.

---

## TC-005 — Case-insensitive city search

**Test Data:** `kYiV`

**Result:** ✅ PASS

The system successfully finds Kyiv regardless of the letter case used in the search query.

---

## TC-006 — Search with an empty query

**Test Data:** Empty input

**Result:** ✅ PASS

No search request is performed and the application remains in a stable state.

No notification is displayed because no specific message for an empty query is required by the current test case.

---

## TC-007 — Search using special characters

**Test Data:** `@@$$!!`

**Result:** ✅ PASS

The system does not return a city and remains stable without breaking the interface.

---

## TC-008 — Search with leading and trailing spaces

**Test Data:** `  Kyiv  `

**Result:** ✅ PASS

The system successfully processes the query and finds Kyiv.

---

## TC-009 — Search with a typo

**Test Data:** `Kyv`

**Result:** ✅ PASS

The system does not return a city and displays the `City not found` notification.

Fuzzy search or automatic typo correction is not required by the current test case.

---

## TC-010 — Search using the wrong keyboard layout

**Test Data:** `Лншм`

**Result:** ✅ PASS

The system does not return a city and displays the `City not found` notification.

Automatic keyboard-layout conversion is not required by the current test case.

---

## TC-011 — Search using a localized city name

**Test Data:** `Київ`

**Result:** ❌ FAIL

The application does not find Kyiv when the city name is entered in Ukrainian.

The same city can be successfully found using the Latin input `Kyiv`.

**Bug:** [BUG-001](../Bug-Reports/BUG-001.md)

**Severity:** High
**Priority:** High

---

## TC-012 — Search using mixed Latin and Cyrillic characters

**Test Data:** `Kиїв`

**Result:** ✅ PASS

The application handles the mixed-character input without breaking and does not return an incorrect result.

---

## TC-013 — Search using digits

**Test Data:** `Kyiv123`

**Result:** ✅ PASS

The system does not return an incorrect city and displays the `City not found` notification.

---

## TC-014 — Search using emoji

**Test Data:** `Kyiv 🇺🇦`

**Result:** ✅ PASS

The application remains stable and successfully handles the input without breaking the interface.

---

## TC-015 — Search using spaces only

**Test Data:** Spaces only

**Result:** ✅ PASS

No search request is performed and the application remains in a stable state.

---

## TC-016 — Minimum search query length

**Test Data:** `K`, `Ky`, `Kyi`

**Result:** ✅ PASS

The application handles different query lengths according to the implemented search behavior:

* With 1 character, no autocomplete suggestions are displayed and pressing `Enter` does not perform a search.
* With 2 characters, autocomplete suggestions may be displayed when matching results are available, and pressing `Enter` can perform a search.
* With 3 characters, autocomplete suggestions are displayed and pressing `Enter` successfully performs the search.

---

## TC-017 — Maximum search query length

**Test Data:** Queries containing 49, 50, 51 and more characters

**Result:** ❌ FAIL

The expected maximum query length is **50 characters**.

The application accepts input exceeding the defined 50-character limit. During the initial test, a query containing 1000 characters could be entered into the search field.

**Bug:** [BUG-002](../Bug-Reports/BUG-002.md)

**Severity:** Minor
**Priority:** Medium

---

## TC-018 — Display of the selected city and weather data

**Test Data:** `Kyiv`

**Result:** ✅ PASS

After a successful search, the application correctly displays the selected city and the corresponding weather information.

The main weather information is displayed without visible UI errors.

---

## TC-019 — Weather data corresponds to the selected city

**Test Data:** `Kyiv`

**Result:** ✅ PASS

The application displays weather data corresponding to the selected city.

The displayed location and timezone are consistent with Kyiv (`Europe/Kyiv`).

The displayed data was additionally compared with the Open-Meteo response.

---

## TC-020 — `City not found` notification

**Test Data:** Invalid city name

**Result:** ✅ PASS

The application displays the `City not found` notification after an unsuccessful search.

The notification appears at the bottom center of the interface and disappears automatically after approximately 2.2 seconds.

---

## TC-021 — Previous city remains after a failed search

**Test Data:** First search: `Kyiv`
Second search: Invalid city

**Result:** ✅ PASS

After a successful search for Kyiv, performing a search with an invalid city does not remove the previously displayed weather information.

The application remains in a stable state.

---

## TC-022 — Search for a partial city name using Enter

**Test Data:** `Kyi`

**Result:** ✅ PASS

When entering `Kyi` and pressing `Enter` without selecting an autocomplete suggestion, the application performs the search.

The system successfully finds a city matching the entered substring.

---

## TC-023 — Interface localization

**Test Data:** Russian, English and Ukrainian

**Result:** ❌ FAIL

After switching the interface language, most interface elements are translated correctly.

However, **buttons 3 and 7 remain in Russian** when switching between Russian, English and Ukrainian.

**Bug:** [BUG-003](../Bug-Reports/BUG-003.md)

**Severity:** Minor
**Priority:** Medium

---

## TC-024 — Accuracy of current weather data

**Test Data:** London weather data comparison

**Result:** ❌ FAIL

At approximately **14:15**, the application displays weather values that correspond to **00:00** instead of the current hour.

According to the Open-Meteo hourly data at the time of verification:

| Parameter  | Expected |  Actual |
| ---------- | -------: | ------: |
| Cloudiness |     100% |      0% |
| Visibility |  19.5 km | 27.7 km |
| UV Index   |      2.2 |     0.0 |

The displayed values correspond to the beginning of the hourly dataset rather than the current hour.

**Bug:** [BUG-004](../Bug-Reports/BUG-004.md)

**Severity:** Critical
**Priority:** High

---

# 📝 Conclusion

A total of **24 test cases** were executed during the initial test run.

* **20 test cases — PASS**
* **4 test cases — FAIL**
* **0 test cases — PARTIAL**
* **0 test cases — BLOCKED**
* **4 defects were identified**

The identified defects were documented as:

* **BUG-001** — Cyrillic city search does not work correctly
* **BUG-002** — Search field accepts more than 50 characters
* **BUG-003** — Buttons 3 and 7 remain in Russian after changing the interface language
* **BUG-004** — Cloudiness, Visibility and UV Index use data from 00:00 instead of the current hour

The initial test execution was completed on **08.09.2026**.

---

# ➡️ Next Steps

1. Fix the identified defects.
2. Perform retesting of **BUG-001 — BUG-004**.
3. Verify that the reported defects are no longer reproducible.
4. Perform regression testing of the affected functionality.
5. Prepare the final test summary.
