# Test Execution & Reporting – MarketMate Webshop

This document contains the executed test scenarios and bugs found during testing of:
- Product Rating System
- Age Verification
- Shipping Cost Logic

All scenarios follow the Masterschool test execution table format.

---

# Bug 1 – Comment does not show on first review

Scenario: When submitting a rating with a comment for the first time, the comment does not appear on the product page.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|-------|---------|------------------|--------|------|----------------|
| 1 | Login to the website | User successfully logged in | OK |  |  |
| 2 | Purchase a product | Product appears in order history | OK |  |  |
| 3 | Open the purchased product page | Review option available | OK |  |  |
| 4 | Add rating + comment | Comment and rating should appear after submit | NOK (only rating appears) |  |  |

---

# Bug 2 – Add Review and Edit Review have different validation rules

Scenario: Add Review has a 500-character limit, while Edit Review accepts unlimited characters.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|-------|---------|------------------|--------|------|----------------|
| 1 | Open product page | Review section visible | OK |  |  |
| 2 | Click “Add Review” | Add Review modal appears | OK |  |  |
| 3 | Enter more than 500 characters | System should show validation error | OK |  |  |
| 4 | Submit the review | Review should not save with >500 characters | OK |  |  |
| 5 | Click “Edit Review” | Edit Review modal appears | OK |  |  |
| 6 | Enter more than 500 characters | System should show validation error | NOK (system accepts long text) |  |  |

---

# Bug 3 – Shipping fee does not return when cart total drops below 20€

Scenario: Shipping becomes free at ≥20€, but shipping fee does not return when cart total goes below 20€.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|-------|---------|------------------|--------|------|----------------|
| 1 | Add items totaling 20€ or more | Shipping becomes free | OK |  |  |
| 2 | Remove items until total is below 20€ | Shipping fee should appear again | NOK (shipping remains free) |  |  |

---

# Bug 4 – Same error message for all invalid age inputs

Scenario: All invalid age inputs show the same underage message.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|-------|---------|------------------|--------|------|----------------|
| 1 | Open homepage | Age verification popup appears | OK |  |  |
| 2 | Leave age field empty and click Confirm | Should show: "Age is required" | NOK |  |  |
| 3 | Enter “abc” as age and click Confirm | Should show: "Invalid age format" | NOK |  |  |
| 4 | Enter age below 18 (e.g., 17) | Underage message should appear | OK |  |  |
| 5 | Enter unrealistic age (e.g., 200) | Should show: "Invalid age" | NOK |  |  |

---

# Bug 5 – Rating only possible after purchase (requirement unclear)

Scenario: Users cannot rate products unless they have purchased them, but the requirement does not mention this limitation.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|-------|---------|------------------|--------|------|----------------|
| 1 | Login as a regular user | User logged in successfully | OK |  |  |
| 2 | Open any product page | Rating option should be available | Expected: OK |  |  |
| 3 | Try to submit a rating | System should accept rating | NOK (rating blocked unless purchased) |  |  |

---

# Bug 6 – Long comments accepted only in Edit mode

Scenario: Add Review rejects long comments, but Edit Review accepts them.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|-------|---------|------------------|--------|------|----------------|
| 1 | Open product page | Review options visible | OK |  |  |
| 2 | Click “Add Review” | Add Review modal appears | OK |  |  |
| 3 | Enter more than 500 characters | Should show validation error | OK |  |  |
| 4 | Submit the review | Should not save long comment | OK |  |  |
| 5 | Click “Edit Review” | Edit Review modal appears | OK |  |  |
| 6 | Enter more than 500 characters | Should show validation error | NOK (system accepts long text) |  |  |

---

# Bug 7 – Under-age warning appears on non-alcohol products

Scenario: Under-age popup appears even when browsing non-alcohol categories.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|-------|---------|------------------|--------|------|----------------|
| 1 | Login as under-18 user | Login successful | OK |  |  |
| 2 | Browse non-alcohol products | No age popup should appear | NOK (popup appears anyway) |  |  |
| 3 | Browse alcohol products | Age popup should appear | OK |  |  |
