## TEST EXECUTION – MARKET MATE WEBSHOP

---

## FEATURE 1 – PRODUCT RATING SYSTEM

### Test Case 1: Comment not displayed on first submission

| Step# | Action | Expected Result | Actual Result | Status | URL | Link to Issue |
|------:|--------|-----------------|--------------|--------|-----|---------------|
| 1 | Login to the webshop | User is logged in | Logged in | PASS | https://grocerymate.masterschool.com | |
| 2 | Navigate to products page | Products page opens | Opened | PASS | | |
| 3 | Select a purchased product | Product page opens | Opened | PASS | | |
| 4 | Click Add Review | Review form opens | Opened | PASS | | |
| 5 | Select rating (4 stars) | Rating selected | Selected | PASS | | |
| 6 | Enter comment | Comment accepted | Accepted | PASS | | |
| 7 | Click Submit | Rating and comment displayed | Comment not displayed | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/1 |

---

### Test Case 2: Comment disappears after page refresh

| Step# | Action | Expected Result | Actual Result | Status | URL | Link to Issue |
|------:|--------|-----------------|--------------|--------|-----|---------------|
| 1 | Login to the webshop | User is logged in | Logged in | PASS | https://grocerymate.masterschool.com | |
| 2 | Open product with submitted rating | Product page opens | Opened | PASS | | |
| 3 | Verify existing rating | Rating visible | Visible | PASS | | |
| 4 | Refresh the page | Rating and comment remain visible | Comment missing | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/1 |

---

## FEATURE 2 – AGE VERIFICATION

### Test Case 3: Same error message shown for all invalid age inputs

| Step# | Action | Expected Result | Actual Result | Status | URL | Link to Issue |
|------:|--------|-----------------|--------------|--------|-----|---------------|
| 1 | Navigate to Alcohol category | Age popup appears | Appeared | PASS | https://grocerymate.masterschool.com/category/alcohol | |
| 2 | Leave age field empty | Specific validation message | Generic underage message | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/4 |
| 3 | Enter invalid text (abc) | Invalid format message | Same generic message | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/4 |

---

### Test Case 4: Underage user blocked from non-alcohol categories

| Step# | Action | Expected Result | Actual Result | Status | URL | Link to Issue |
|------:|--------|-----------------|--------------|--------|-----|---------------|
| 1 | Enter age below 18 | Access restricted to alcohol only | Age accepted | FAIL | https://grocerymate.masterschool.com | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/5 |
| 2 | Navigate to normal products | Products visible | Products blocked | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/5 |

---

## FEATURE 3 – SHIPPING COST

### Test Case 5: Shipping fee does not return after cart total drops below threshold

| Step# | Action | Expected Result | Actual Result | Status | URL | Link to Issue |
|------:|--------|-----------------|--------------|--------|-----|---------------|
| 1 | Add items until total ≥ 20€ | Free shipping applied | Applied | PASS | https://grocerymate.masterschool.com/cart | |
| 2 | Remove item from cart | Shipping fee added | Still free | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/3 |
| 3 | Refresh cart page | Shipping fee persists | Still free | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/3 |

---

### Test Case 6: Shipping cost not recalculated dynamically

| Step# | Action | Expected Result | Actual Result | Status | URL | Link to Issue |
|------:|--------|-----------------|--------------|--------|-----|---------------|
| 1 | Start with cart total below 20€ | Shipping fee applied | Applied | PASS | https://grocerymate.masterschool.com/cart | |
| 2 | Add item to reach ≥ 20€ | Shipping becomes free | Still charged | FAIL | | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/3 |
