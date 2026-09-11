# 🐛 Bug Report

**Bug ID:** BUG-001

## 💻 Environment

* **OS:** Windows 11
* **Browser:** Chrome
* **Environment:** Production

## 🔄 Preconditions

* Weather Forecast application is opened.
* The city search field is available.

## 📝 Steps to Reproduce

1. Enter `Київ` into the city search field.
2. Press **Enter**.
3. Observe the search result.

## 🎯 Expected Result

The system should successfully find the existing city and display weather data for Kyiv.

## 💥 Actual Result

The system does not find the city and displays the **"City not found"** toast message.

## 📊 Severity and Priority

* **Severity:** High
* **Priority:** High

## 📸 Evidence
<img width="1919" height="994" alt="Image" src="https://github.com/user-attachments/assets/dc1e1834-fef3-4f8f-8eb9-0ef70e4f0252" />
<!-- Attach a screenshot showing "Київ" in the search field and the "City not found" message. -->

## 🛠️ Additional Context

Searching for the same city using the English name `Kyiv` works correctly, while searching using the Ukrainian name `Київ` returns the **"City not found"** message.

## 🔗 Related Test Case

**TC-011 — Search for a city in different languages**
