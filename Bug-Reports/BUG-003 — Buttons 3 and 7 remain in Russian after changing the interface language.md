# 🐛 Bug Report

**Bug ID:** BUG-003

## 💻 Environment

* **OS:** Windows 11
* **Browser:** Chrome
* **Environment:** Production

## 🔄 Preconditions

* Weather Forecast application is opened.
* The interface is available in Russian, English and Ukrainian.
* Language switcher is available.

## 📝 Steps to Reproduce

1. Open the Weather Forecast application.
2. Set the interface language to Russian.
3. Switch the interface language to English.
4. Check the text of buttons **3** and **7**.
5. Switch the interface language to Ukrainian.
6. Check the text of buttons **3** and **7** again.

## 🎯 Expected Result

All localized interface elements, including buttons **3** and **7**, should be displayed in the currently selected language.

When English is selected, the buttons should display English text.

When Ukrainian is selected, the buttons should display Ukrainian text.

## 💥 Actual Result

When switching the interface to English or Ukrainian, the text of buttons **3** and **7** remains in Russian.

Other interface elements are translated according to the selected language.

## 📊 Severity and Priority

* **Severity:** Minor
* **Priority:** Medium

## 📸 Evidence

<img width="1912" height="990" alt="Image" src="https://github.com/user-attachments/assets/48c59c10-e241-4385-abe6-1de192881a06" />

<img width="1916" height="994" alt="Image" src="https://github.com/user-attachments/assets/7eae9641-2732-41f1-b507-cd6b8b03d300" />

## 🛠️ Additional Context

The issue affects only specific interface elements. The language switching functionality itself works, but buttons **3** and **7** are not localized correctly.

## 🔗 Related Test Case

**TC-023 — Проверка локализации элементов интерфейса**
