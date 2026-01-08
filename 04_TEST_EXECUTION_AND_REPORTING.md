# Test Execution – MarketMate (Based on Test Case Design)

This document records the execution results of the test cases designed for the 3 new features:
1) Product Rating System
2) Age Verification for Alcoholic Products
3) Shipping Cost Changes

---

# Feature 1: Product Rating System – Test Execution

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|------|--------|------------------|--------|-----|---------------|
| 1 | Open a product page that allows review (after purchase) | Review section is visible | OK |  |  |
| 2 | (BVA) Select rating = 1 and submit | Rating is submitted successfully | OK |  |  |
| 3 | (BVA) Select rating = 5 and submit | Rating is submitted successfully | OK |  |  |
| 4 | (EP) Try rating = 0 | Error message “Invalid rating value.” | OK |  |  |
| 5 | (EP) Try rating = 6 | Error message “Invalid rating value.” | OK |  |  |
| 6 | (EG) Submit without selecting stars | Error message “Rating is required.” | OK |  |  |
| 7 | (EG) Enter invalid characters “five” in rating | Error message “Invalid rating format.” | OK |  |  |
| 8 | (Use Case) Submit rating + comment | Rating and comment saved and displayed under product | NOK (comment missing) |  |  |
| 9 | (Use Case) Submit new rating to check average update | Average rating recalculated and displayed correctly |  |  |  |

---

# Feature 2: Age Verification for Alcoholic Products – Test Execution

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|------|--------|------------------|--------|-----|---------------|
| 1 | Navigate to Alcohol category | Age verification modal appears | OK |  |  |
| 2 | (BVA) Enter age = 18 and confirm | Access allowed | OK |  |  |
| 3 | (BVA) Enter age = 17 and confirm | Access denied, message “You must be 18+.” | OK |  |  |
| 4 | (EP) Enter age = 15 and confirm | Access denied | OK |  |  |
| 5 | (EP) Enter age = 25 and confirm | Access granted | OK |  |  |
| 6 | (EG) Leave age field empty and confirm | Error message “Age is required.” | NOK (same underage msg) |  |  |
| 7 | (EG) Enter “abc” and confirm | Error message “Invalid age format.” | NOK (same underage msg) |  |  |
| 8 | (Use Case) Navigate to Alcohol category again | Age modal appears before accessing Alcohol section | OK |  |  |
| 9 | (Use Case) Enter age = 16 | User remains blocked from Alcohol category | OK |  |  |

---

# Feature 3: Shipping Cost Changes – Test Execution

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|------|--------|------------------|--------|-----|---------------|
| 1 | (BVA) Set cart total = 20.00€ | Free shipping is applied | OK |  |  |
| 2 | (BVA) Set cart total = 19.99€ | Shipping fee is added | OK |  |  |
| 3 | (EP) Set cart total = 35€ | Free shipping is applied | OK |  |  |
| 4 | (EP) Set cart total = 10€ | Shipping fee is added | OK |  |  |
| 5 | (Use Case) Start with total ≥ 20€, then remove item so total < 20€ | Shipping fee is added automatically | NOK (fee does not return) |  |  |
| 6 | (Use Case) Start with total < 20€, then add items so total ≥ 20€ | Free shipping is applied | OK |  |  |
