# Regression Report

## Overview

* **Project:** Weather Forecast
* **Regression Date:** 13.09.2026
* **Tester:** Rohachevsk
* **Environment:** Windows 11, Chrome, Production

## Regression Scope

A short regression run was performed after fixing BUG-001, BUG-002, BUG-003 and BUG-004.

The regression focused on the functionality affected by the fixes and related application areas:

* City search
* Search input validation
* Current weather data
* Forecast data
* Interface localization

## Regression Results

| Test Case | Description                                                                         | Status   |
| --------- | ----------------------------------------------------------------------------------- | -------- |
| TC-001    | Search for a valid city and verify that weather data is displayed correctly         | **PASS** |
| TC-003    | Search for another valid city and verify that the correct weather data is displayed | **PASS** |
| TC-006    | Verify that current weather information is displayed correctly                      | **PASS** |
| TC-008    | Verify hourly forecast data and its correct display                                 | **PASS** |
| TC-009    | Verify 3-day and 7-day forecast functionality                                       | **PASS** |
| TC-011    | Search for a city using different supported languages                               | **PASS** |
| TC-017    | Verify the maximum allowed search query length                                      | **PASS** |
| TC-020    | Switch the interface between supported languages                                    | **PASS** |
| TC-023    | Verify localization of interface elements                                           | **PASS** |
| TC-024    | Verify that Cloudiness, Visibility and UV Index correspond to the current hour      | **PASS** |

## Summary

**10/10 selected regression test cases passed.**

No new defects were found during the regression run.

All previously fixed defects remained resolved, and no regressions were identified in the tested functionality.

## Conclusion

The regression testing was completed successfully.

The implemented fixes did not negatively affect the tested functionality of the Weather Forecast application.
