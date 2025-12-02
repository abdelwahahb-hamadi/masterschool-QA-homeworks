# Test Execution & Reporting – MarketMate Webshop

This document includes the executed test scenarios and bugs found during testing of:
- Age Verification
- Product Rating System
- Shipping Cost Logic

Each bug is documented using the Masterschool table format.

---

---

## 🐞 Bug 1 – Comment Not Showing on First Review

### Scenario  
As a user, when I submit a rating with a comment for the first time, the comment should appear under the product.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|------|--------|------------------|--------|-----|----------------|
| 1 | Login as valid user | User logged in | OK |  |  |
| 2 | Purchase product | Product appears in order history | OK |  |  |
| 3 | Open purchased product page | Review section visible | OK |  |  |
| 4 | Add rating + comment | Comment + stars should show in preview | OK |  |  |
| 5 | Submit review | Comment should appear under product | NOK |  |  |

---

## 🐞 Bug 2 – Add Review vs Edit Review Validation Mismatch

### Scenario  
Add Review blocks inputs over 500 characters, Edit Review accepts unlimited text.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|------|--------|------------------|--------|-----|----------------|
| 1 | Open product page | Review form visible | OK |  |  |
| 2 | Click “Add Review” | Add modal opens | OK |  |  |
| 3 | Enter 600 chars | Should show validation error | OK |  |  |
| 4 | Save review | Review should save with max 500 chars | OK |  |  |
| 5 | Click “Edit Review” | Edit modal opens | OK |  |  |
| 6 | Enter 600 chars | Should block long text | NOK |  |  |

---

## 🐞 Bug 3 – Shipping Fee Does Not Return When Cart < 20€

### Scenario  
Shipping should become paid again when cart drops below 20€, but it doesn't.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|------|--------|------------------|--------|-----|----------------|
| 1 | Add items ≥ 20€ | Shipping becomes free | OK |  |  |
| 2 | Remove items until < 20€ | Shipping fee should reappear | NOK |  |  |

---

## 🐞 Bug 4 – Same Error Message for All Age Input Cases

### Scenario  
All invalid inputs show the same under-age message.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|------|--------|------------------|--------|-----|----------------|
| 1 | Open age popup | Popup visible | OK |  |  |
| 2 | Leave age empty | “Age required” | NOK |  |  |
| 3 | Enter “abc” | “Invalid format” | NOK |  |  |
| 4 | Enter <18 | “You must be 18+” | OK |  |  |
| 5 | Enter age >120 | “Invalid age” | NOK |  |  |

---

## 🐞 Bug 5 – Rating Only Possible After Purchase (Unclear Requirement)

### Scenario  
System blocks rating unless product is purchased, but requirement does not state this.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|------|--------|------------------|--------|-----|----------------|
| 1 | Login as user | Logged in | OK |  |  |
| 2 | Open product page | Rating option visible | Expected: Visible |  |  |
| 3 | Try to rate | Should allow rating | NOK |  |  |

---

## 🐞 Bug 6 – Long Comments Accepted Only In Edit Mode

### Scenario  
Add Review rejects long text, Edit Review accepts it.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|------|--------|------------------|--------|-----|----------------|
| 1 | Open Add Review | Modal opens | OK |  |  |
| 2 | Enter 600 chars | Should show error | OK |  |  |
| 3 | Submit | Should not save | OK |  |  |
| 4 | Open Edit Review | Modal opens | OK |  |  |
| 5 | Enter 600 chars | Should show error | NOK |  |  |

---

## 🐞 Bug 7 – Under-Age Warning Appears On Non-Alcohol Products

### Scenario  
Warning popup appears even when browsing non-alcohol products.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|------|--------|------------------|--------|-----|----------------|
| 1 | Login as under-18 user | Login successful | OK |  |  |
| 2 | Open non-alcohol product | No popup should appear | NOK |  |  |
| 3 | Open alcohol product | Popup should appear | OK |  |  |

---
