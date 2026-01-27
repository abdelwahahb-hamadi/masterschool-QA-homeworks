## TEST EXECUTION – MARKET MATE WEBSHOP (UPDATED)

---

## FEATURE 1 – PRODUCT RATING SYSTEM

### Test Case 1: Comment not displayed on first submission (after purchase)

| Step# | Action | Expected Result | Actual Result | Status | URL | Link to Issue |
|------:|--------|-----------------|--------------|--------|-----|---------------|
| 1 | Go to login page | Login page opens | Opened | PASS | https://grocerymate.masterschool.com/login | |
| 2 | Enter valid credentials | Credentials accepted | Accepted | PASS | | |
| 3 | Click Sign In | User logged in | Logged in | PASS | https://grocerymate.masterschool.com | |
| 4 | Go to Shop / Products | Products list is visible | Visible | PASS | https://grocerymate.masterschool.com/shop | |
| 5 | Open a product | Product page opens | Opened | PASS | | |
| 6 | Add product to cart | Product added to cart | Added | PASS | | |
| 7 | Go to cart | Cart page opens | Opened | PASS | https://grocerymate.masterschool.com/cart | |
| 8 | Complete checkout | Order completed successfully | Completed | PASS | | |
| 9 | Open the same product page again | Product page opens | Opened | PASS | | |
|10 | Click Add Review | Review modal opens | Opened | PASS | | |
|11 | Select rating (4 stars) | Rating selected | Selected | PASS | | |
|12 | Enter comment | Comment accepted | Accepted | PASS | | |
|13 | Click Submit | Rating + comment displayed | Comment not displayed | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/1 |

---

### Test Case 2: Comment disappears after refresh (rating exists, comment missing)

| Step# | Action | Expected Result | Actual Result | Status | URL | Link to Issue |
|------:|--------|-----------------|--------------|--------|-----|---------------|
| 1 | Go to login page | Login page opens | Opened | PASS | https://grocerymate.masterschool.com/login | |
| 2 | Enter valid credentials | Credentials accepted | Accepted | PASS | | |
| 3 | Click Sign In | User logged in | Logged in | PASS | https://grocerymate.masterschool.com | |
| 4 | Go to Shop / Products | Products list is visible | Visible | PASS | https://grocerymate.masterschool.com/shop | |
| 5 | Open the product that has a submitted rating | Product page opens | Opened | PASS | | |
| 6 | Verify rating and comment are visible | Rating + comment visible | Only rating visible | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/1 |
| 7 | Refresh the page | Rating + comment still visible | Comment still missing | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/1 |

---

## FEATURE 2 – AGE VERIFICATION

### Test Case 3: Same error message for empty age and invalid text

| Step# | Action | Expected Result | Actual Result | Status | URL | Link to Issue |
|------:|--------|-----------------|--------------|--------|-----|---------------|
| 1 | Go to login page | Login page opens | Opened | PASS | https://grocerymate.masterschool.com/login | |
| 2 | Enter valid credentials | Credentials accepted | Accepted | PASS | | |
| 3 | Click Sign In | User logged in | Logged in | PASS | https://grocerymate.masterschool.com | |
| 4 | Navigate to Alcohol category | Age modal appears | Appeared | PASS | https://grocerymate.masterschool.com/category/alcohol | |
| 5 | Leave age field empty and confirm | Required/validation message shown | Same generic message shown | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/4 |
| 6 | Enter invalid text (abc) and confirm | Invalid format message shown | Same generic message shown | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/4 |

---

### Test Case 4: Underage user blocked outside alcohol category

| Step# | Action | Expected Result | Actual Result | Status | URL | Link to Issue |
|------:|--------|-----------------|--------------|--------|-----|---------------|
| 1 | Go to login page | Login page opens | Opened | PASS | https://grocerymate.masterschool.com/login | |
| 2 | Enter valid credentials | Credentials accepted | Accepted | PASS | | |
| 3 | Click Sign In | User logged in | Logged in | PASS | https://grocerymate.masterschool.com | |
| 4 | Navigate to Alcohol category | Age modal appears | Appeared | PASS | https://grocerymate.masterschool.com/category/alcohol | |
| 5 | Enter age below 18 and confirm | Only alcohol access blocked | User blocked beyond alcohol (unexpected) | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/5 |
| 6 | Navigate to normal products (Shop) | Normal products visible | Normal products blocked | FAIL | https://grocerymate.masterschool.com/shop | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/5 |

---

## FEATURE 3 – SHIPPING COST

### Test Case 5: Shipping fee does not return after dropping below 20€

| Step# | Action | Expected Result | Actual Result | Status | URL | Link to Issue |
|------:|--------|-----------------|--------------|--------|-----|---------------|
| 1 | Go to login page | Login page opens | Opened | PASS | https://grocerymate.masterschool.com/login | |
| 2 | Enter valid credentials | Credentials accepted | Accepted | PASS | | |
| 3 | Click Sign In | User logged in | Logged in | PASS | https://grocerymate.masterschool.com | |
| 4 | Go to Shop / Products | Products list visible | Visible | PASS | https://grocerymate.masterschool.com/shop | |
| 5 | Add items until cart total ≥ 20€ | Free shipping applied | Applied | PASS | | |
| 6 | Open cart page | Cart page opens | Opened | PASS | https://grocerymate.masterschool.com/cart | |
| 7 | Remove item so total becomes < 20€ | Shipping fee appears again | Shipping stays free | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/3 |
| 8 | Refresh cart page | Shipping fee still correct | Shipping still free | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/3 |

---

### Test Case 6: Shipping cost not recalculated correctly when adding/removing items

| Step# | Action | Expected Result | Actual Result | Status | URL | Link to Issue |
|------:|--------|-----------------|--------------|--------|-----|---------------|
| 1 | Go to login page | Login page opens | Opened | PASS | https://grocerymate.masterschool.com/login | |
| 2 | Enter valid credentials | Credentials accepted | Accepted | PASS | | |
| 3 | Click Sign In | User logged in | Logged in | PASS | https://grocerymate.masterschool.com | |
| 4 | Go to Shop / Products | Products list visible | Visible | PASS | https://grocerymate.masterschool.com/shop | |
| 5 | Add item(s) so total is < 20€ | Shipping fee applied | Applied | PASS | | |
| 6 | Go to cart page | Cart page opens | Opened | PASS | https://grocerymate.masterschool.com/cart | |
| 7 | Add more items so total becomes ≥ 20€ | Shipping becomes free | Shipping does not update correctly | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/3 |
