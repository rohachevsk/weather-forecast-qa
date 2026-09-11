# 🐛 Bug Report

**Bug ID:** BUG-004

## 💻 Environment

* **OS:** Windows 11
* **Browser:** Chrome
* **Environment:** Production

## 🔄 Preconditions

* Weather Forecast application is opened.
* A city with available hourly weather data is selected.
* Current weather information is displayed.

## 📝 Steps to Reproduce

1. Open the Weather Forecast application.
2. Search for and select **London**.
3. Note the current time.
4. Open DevTools → **Network** and locate the Open-Meteo weather request.
5. Check the `current.time` value in the response.
6. Check the hourly `time` array.
7. Compare the application's **Cloudiness**, **Visibility** and **UV Index** values with the hourly data for the current hour and `00:00`.

## 🎯 Expected Result

Cloudiness, Visibility and UV Index should correspond to the hourly weather data for the **current hour**.

For example, when:

`current.time = 2026-09-09T05:45`

the application should use the hourly data for:

`2026-09-09T05:00`

because the hourly dataset is provided with hourly timestamps.

## 💥 Actual Result

The application uses the first record of the hourly dataset (`00:00`) instead of the hourly record corresponding to the current time.

During the test, Open-Meteo returned:

* `current.time`: `2026-09-09T09:15`
* hourly records included: `09:00`, `10:00`, etc.
* the first hourly record: `00:00`

The application's logic attempts to find an exact match for `09:15` in the hourly timestamps. Since the hourly data contains `05:00` rather than `05:45`, no exact match is found.

The implementation then falls back to index `0`, which corresponds to `00:00`.

As a result, Cloudiness, Visibility and UV Index may be taken from the midnight record instead of the current hourly record.

## 📊 Severity and Priority

* **Severity:** Major
* **Priority:** High

## 📸 Evidence

<img width="1916" height="990" alt="Image" src="https://github.com/user-attachments/assets/f2bef21f-fde1-4f74-b90e-a0cc5d4cc576" />

<img width="1919" height="990" alt="Image" src="https://github.com/user-attachments/assets/6027c727-655f-4c23-a952-d120c6cca1a2" />

<img width="1917" height="987" alt="Image" src="https://github.com/user-attachments/assets/b2852470-64cb-4500-8163-396dd864bfdb" />

## 🛠️ Additional Context

The issue affects the selection of the following weather parameters: Cloudiness, Visibility and UV Index. In this test, the mismatch was directly observed for Cloudiness and Visibility.

The API provides the current time with minute precision (`09:15`), while hourly weather data is provided at exact hourly timestamps (`09:00`, `10:00`, etc.).

When an exact timestamp match is not found, the application falls back to the first hourly record.

This can result in displaying outdated weather information from `00:00` instead of the current hour.

The issue affects the following weather parameters:

* Cloudiness
* Visibility
* UV Index

## 🔗 Related Test Case

**TC-024 — Точность: облачность, видимость и UV Index**
