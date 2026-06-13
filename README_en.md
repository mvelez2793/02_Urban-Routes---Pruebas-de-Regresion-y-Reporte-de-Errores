<div align="right">
  🌍 <a href="README.md">Español</a> | <strong>English</strong>
</div>

# 🚦 Urban Routes: Regression Testing and Bug Reporting

![Urban Routes App](https://img.shields.io/badge/Project-Regression_Testing-blue) ![Status](https://img.shields.io/badge/Status-Completed-success) ![Tool](https://img.shields.io/badge/Tool-Jira_/_Google_Sheets-green)

## 📌 Project Summary

*   **Situation:** **Urban Routes** is a transportation application that creates routes and calculates trip duration and price for different types of transport (personal vehicle, taxi, bicycle, etc.) based on "From" (A) and "To" (B) points. The team needed to guarantee the quality of the interface and routing logic before a production release.
*   **Task:** Execute detailed regression tests on the user interface and map functionality, identify discrepancies against design requirements, and report bugs to the development team.
*   **Action:** Executed an exhaustive test plan covering map interaction, address fields, and view modes (Street View, Satellite, Terrain). Documented each execution by assigning precise statuses and recorded Bug Reports with reproduction steps, expected vs. actual results, and severity levels.
*   **Result:** Successfully isolated and reported multiple defects, including **Critical** errors that prevented zooming on addresses and **Minor** UI errors. This provided the development team with the exact evidence needed to fix critical issues before they affected the end-user experience.

---

## 🧪 Technical Showcase: Test Case Design

Below is an example of how I structure my test cases, ensuring that any team member can understand the precondition and expected results:

| ID | Test Case Title | Precondition | Steps | Expected Result | Status | Bug ID |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **CASE-5** | "From" field can be selected | Open the Urban Routes application | 1. Click on the "From" field. | The "From" field is selected. The cursor blinks. The search field is empty. | ❌ Failed | BR1-01 |

*Note: Extracted from the functional regression test suite.*

---

## 🐛 Technical Showcase: Bug Reporting (Bug Life Cycle)

When a test case fails, my approach is to provide developers with an unambiguous report. Here is an example of a critical defect found during regression testing:

| Bug ID | Title | Severity |
| :--- | :--- | :--- |
| **BR1-02** | The map does not zoom into the address after completing the "From" field | 🔴 Critical |

**Steps to reproduce:**
1. Open the Urban Routes application.
2. Make sure the "From" field is empty.
3. Click on the "From" field.
4. Enter a valid address (example: East 2nd Street, 601).

**Expected Result:**
The map zooms in on the selected address pin. The view must match the design description.

**Actual Result:**
When entering the address in the "From" field, the application does not perform the search or the expected zoom.

---
*🧑‍💻 Technical Profile: María Auxiliadora Vélez Mendoza - QA Engineer*
