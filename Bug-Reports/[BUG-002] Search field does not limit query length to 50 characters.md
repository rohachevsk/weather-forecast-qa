# 🐛 Bug Report

**Bug ID:** BUG-002

## 💻 Environment

* **OS:** Windows 11
* **Browser:** Chrome
* **Environment:** Production

## 🔄 Preconditions

* Weather Forecast application is opened.
* The city search field is available.

## 📝 Steps to Reproduce

1. Enter a search query containing more than 50 characters into the city search field.
2. For example, enter a string containing 1000 characters.
3. Observe the search field.

## 🎯 Expected Result

The search field should allow entering a maximum of **50 characters**.

Characters exceeding the 50-character limit should not be accepted.

## 💥 Actual Result

The search field accepts a search query containing more than 50 characters without any limitation.

## 📊 Severity and Priority

* **Severity:** Medium
* **Priority:** Medium

## 📸 Evidence

<img width="1918" height="990" alt="Image" src="https://github.com/user-attachments/assets/a12ca9f1-8e21-4d20-86e0-b2f466caf22a" />

<!-- Attach a screenshot showing a search query containing more than 50 characters. -->

## 🛠️ Additional Context

The maximum allowed length of the search query is defined as **50 characters**.

The current implementation does not restrict the number of characters that can be entered into the search field.

## 🔗 Related Test Case

**TC-017 — Максимальная длина поискового запроса**
