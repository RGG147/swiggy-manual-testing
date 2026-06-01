# Manual Testing Project – Swiggy (Food Delivery App)

**Tester:** Raghav Gaur  
**Testing Type:** Manual Testing (Functional + UI + Edge Case)  
**Platform Tested:** Swiggy Android App (v4.x) + Web (Chrome)  
**Test Duration:** May 2026  
**Tools Used:** Manual observation, Excel (test case documentation), Android device, Chrome browser  

---

## Objective

The goal of this project was to manually test core user-facing flows of the Swiggy food delivery application — covering the Login, Search & Discovery, Cart, and Checkout modules — to identify functional gaps, UI inconsistencies, and edge case failures that could impact user experience and order conversion.

---

## Scope of Testing

| Module | Testing Focus |
|---|---|
| Login & Authentication | OTP flow, invalid inputs, session handling |
| Search & Restaurant Discovery | Search accuracy, filters, empty states |
| Cart Management | Add/remove items, quantity update, price calculation |
| Checkout & Address | Address selection, coupon application, payment navigation |

---

## Folder Structure

```
swiggy-manual-testing/
│
├── README.md                  ← You are here
├── Test_Cases_Swiggy.xlsx     ← All 20 test cases with steps and expected results  
├── Bug_Report_Swiggy.xlsx     ← 6 bugs logged with severity, steps, and screenshots notes
└── Test_Summary_Report.md     ← Overall test execution summary
```

---

## Test Execution Summary

| Total Test Cases | Passed | Failed | Blocked |
|---|---|---|---|
| 20 | 14 | 5 | 1 |

**Pass Rate: 70%**

---

## Key Bugs Found

| Bug ID | Module | Summary | Severity |
|---|---|---|---|
| BUG-001 | Cart | Price total not updating on item quantity change | High |
| BUG-002 | Search | Search returns no results for partial restaurant name | Medium |
| BUG-003 | Login | OTP resend button active before 30s timer completes | Medium |
| BUG-004 | Checkout | Coupon error message not cleared after entering valid code | Low |
| BUG-005 | Cart | "Remove" button unresponsive on first tap (Android) | High |
| BUG-006 | Address | App crashes when special characters entered in address field | High |

---

## Skills Demonstrated

- Writing structured test cases from feature requirements
- Identifying and documenting bugs with reproducible steps
- Functional, UI, and edge case testing
- Cross-platform testing (Android app + Web browser)
- Severity and priority classification of defects

---

## Notes

This is a self-initiated manual testing project done for learning and skill demonstration purposes. Swiggy is a publicly available application. No internal systems, APIs, or private data were accessed.
