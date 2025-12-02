# TEST_EXECUTION_AND_REPORTING – Market Mate Webshop

Below are the test execution tables and bug lists for the new features:
Age Verification, Product Rating, and Shipping Fee Logic.

---

## 1. Age Verification – Test Execution

### Scenario  
As a user, I should only be able to access alcohol products if my age is 18 or above.

### Test Scenario – Invalid Age Inputs (with bugs)

| Step# | Action                                       | Expected Outcome                                                                 | OK/NOK | URL              | Link to issue |
|------:|----------------------------------------------|----------------------------------------------------------------------------------|:------:|------------------|---------------|
| 1     | Open website                                 | Homepage loads                                                                   |  OK    | `/`              |               |
| 2     | Try to access **Alcohol** category           | Age verification popup appears                                                   |  OK    | `/alcohol`       |               |
| 3a    | Leave age field **empty**                    | Should show specific error message like “Age is required”                        | **NOK** |                  | `BUG-AGE-01`  |
| 3b    | Enter invalid text `"abc"` as birth date     | Should show “Invalid date format”                                                | **NOK** |                  | `BUG-AGE-01`  |
| 3c    | Enter valid but **underage** date (17 years) | Should show “You must be 18+” and block access                                  |  OK    |                  |               |
| 3d    | Enter valid **18+** birth date               | Should allow access to alcohol products                                          |  OK    |                  |               |
| 4     | Browse normal products as underage user      | Warning should NOT appear outside alcohol category                               | **NOK** | `/shop`          | `BUG-AGE-02`  |

### Age Verification – Bug List

| Bug ID     | Description                                                                                       | Severity |
|-----------|---------------------------------------------------------------------------------------------------|---------|
| BUG-AGE-01 | Same “underage” error message is used for **all** invalid inputs (empty, text, bad format, under 18) | Medium  |
| BUG-AGE-02 | Under-age warning appears even when browsing **non-alcohol** products                              | High    |

---

## 2. Product Rating – Test Execution

### Scenario  
As a logged-in user who bought a product, I should be able to add a rating and a comment.

### Test Scenario – Add & Edit Review (with bugs)

| Step# | Action                                              | Expected Outcome                                                              | OK/NOK | URL           | Link to issue |
|------:|-----------------------------------------------------|-------------------------------------------------------------------------------|:------:|---------------|---------------|
| 1     | Login                                               | User is logged in                                                             |  OK    | `/login`      |               |
| 2     | Buy a product                                       | Order completed successfully                                                  |  OK    | `/checkout`   |               |
| 3     | Open the product details page                       | Rating section and “Add a comment” form are visible                           |  OK    | `/product/ID` |               |
| 4a    | Add 5 stars + a text comment (first review)         | Stars and comment should both appear under reviews                            | **NOK** |               | `BUG-RATE-01` |
| 4b    | In **Add Review**, enter comment > 500 characters   | Input should be rejected or blocked with clear validation message             |  OK    |               |               |
| 5a    | Open **Edit Review** for existing rating            | Form opens with current stars and comment                                     |  OK    |               |               |
| 5b    | In **Edit Review**, enter very long comment (>500)  | Should follow same 500-char rule as Add Review                                | **NOK** |               | `BUG-RATE-02` |

### Product Rating – Bug List

| Bug ID      | Description                                                                                         | Severity |
|------------|-----------------------------------------------------------------------------------------------------|---------|
| BUG-RATE-01 | First-time **Add Review** saves only stars; the comment text is not shown on the product page        | High    |
| BUG-RATE-02 | **Edit Review** accepts long comments with no limit, while Add Review is limited to 500 characters   | Medium  |

---

## 3. Shipping Fee Logic – Test Execution

### Scenario  
As a user, shipping should be free only when the cart total is **20€ or more**.  
If the cart total is below 20€, a shipping fee should be added.

### Test Scenario – Shipping Recalculation (with bug)

| Step# | Action                                         | Expected Outcome                                                | OK/NOK | URL      | Link to issue |
|------:|------------------------------------------------|-----------------------------------------------------------------|:------:|----------|---------------|
| 1     | Add items until cart total = **19.99€**        | Shipping fee (e.g. 5€) is shown                                |  OK    | `/cart`  |               |
| 2     | Add more items to reach **≥ 20€**              | Shipping fee is removed – order qualifies for free shipping     |  OK    | `/cart`  |               |
| 3     | Remove items so total goes back **below 20€**  | Shipping fee should appear again                                | **NOK** | `/cart` | `BUG-SHIP-01` |

### Shipping – Bug List

| Bug ID       | Description                                                                      | Severity |
|-------------|----------------------------------------------------------------------------------|---------|
| BUG-SHIP-01 | After free shipping is applied once (≥ 20€), removing items below 20€ **does not bring back** the shipping fee | High    |

---

## 4. Overall Test Summary

| Area              | Result                                    | Notes                                              |
|-------------------|-------------------------------------------|----------------------------------------------------|
| Age Verification  | Partially working, 2 bugs found           | Same error for all cases, warning shows too often |
| Product Rating    | Core flow works but inconsistent behavior | Comment not saved first time, Edit rules differ   |
| Shipping Logic    | Threshold logic partly works, 1 bug found | Fee not restored after cart drops below 20€       |
