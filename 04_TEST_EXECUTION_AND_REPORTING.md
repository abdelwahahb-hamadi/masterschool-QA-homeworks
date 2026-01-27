## FEATURE 1 – PRODUCT RATING SYSTEM

### Test Case 1: Add rating and comment after purchase (Happy Path)

| Step# | Action | Expected Result | Actual Result | Status (PASS/FAIL) | URL | Evidence | Link to Issue |
|------:|--------|-----------------|--------------|--------------------|-----|----------|--------------|
| 1 | Login to the webshop | User is logged in |  |  | https://webshop.example.com/login |  |  |
| 2 | Navigate to products page | Products page opens |  |  | https://webshop.example.com/products |  |  |
| 3 | Select a product | Product page opens |  |  | https://webshop.example.com/product/123 |  |  |
| 4 | Add product to cart | Product added to cart |  |  | https://webshop.example.com/cart |  |  |
| 5 | Complete checkout | Order completed |  |  | https://webshop.example.com/checkout |  |  |
| 6 | Open product page again | Product page opens |  |  | https://webshop.example.com/product/123 |  |  |
| 7 | Click Add Review | Review form opens |  |  | https://webshop.example.com/product/123#reviews |  |  |
| 8 | Select rating (4 stars) | Rating selected |  |  | https://webshop.example.com/product/123#reviews |  |  |
| 9 | Enter comment | Comment accepted |  |  | https://webshop.example.com/product/123#reviews |  |  |
|10 | Click Submit | Rating and comment displayed | Comment not displayed | FAIL | https://webshop.example.com/product/123#reviews |  | https://github.com/abdelwahhab-hamadi/masterschool-QA-homeworks/issues/1 |


### Test Case 2: Comment not displayed on first submission (Bug Case)

| Step# | Action | Expected Result | Actual Result | Status (PASS/FAIL) | URL | Evidence | Link to Issue |
|------:|--------|-----------------|--------------|--------------------|-----|----------|--------------|
| 1 | Login to the webshop | User is logged in |  |  | https://webshop.example.com/login |  |  |
| 2 | Open purchased product page | Product page opens |  |  | https://webshop.example.com/product/123 |  |  |
| 3 | Click Add Review | Review form opens |  |  | https://webshop.example.com/product/123#reviews |  |  |
| 4 | Select rating | Rating selected |  |  | https://webshop.example.com/product/123#reviews |  |  |
| 5 | Enter comment | Comment accepted |  |  | https://webshop.example.com/product/123#reviews |  |  |
| 6 | Click Submit | Rating and comment displayed | Only rating displayed | FAIL | https://webshop.example.com/product/123#reviews |  | https://github.com/abdelwahhab-hamadi/masterschool-QA-homeworks/issues/1 |
| 7 | Refresh page | Comment still visible | Comment missing | FAIL | https://webshop.example.com/product/123#reviews |  | https://github.com/abdelwahhab-hamadi/masterschool-QA-homeworks/issues/1 |


## FEATURE 2 – AGE VERIFICATION

### Test Case 3: Valid age (18 or above)

| Step# | Action | Expected Result | Actual Result | Status (PASS/FAIL) | URL | Evidence | Link to Issue |
|------:|--------|-----------------|--------------|--------------------|-----|----------|--------------|
| 1 | Open webshop home page | Home page opens |  |  | https://webshop.example.com |  |  |
| 2 | Navigate to Alcohol category | Age popup appears |  |  | https://webshop.example.com/alcohol |  |  |
| 3 | Enter age 18 or above | Age accepted |  |  | https://webshop.example.com/alcohol |  |  |
| 4 | Confirm age | Access granted | Access granted | PASS | https://webshop.example.com/alcohol |  |  |


### Test Case 4: Underage or invalid age input

| Step# | Action | Expected Result | Actual Result | Status (PASS/FAIL) | URL | Evidence | Link to Issue |
|------:|--------|-----------------|--------------|--------------------|-----|----------|--------------|
| 1 | Navigate to Alcohol category | Age popup appears |  |  | https://webshop.example.com/alcohol |  |  |
| 2 | Enter age below 18 | Input processed |  |  | https://webshop.example.com/alcohol |  |  |
| 3 | Confirm age | Access denied | Access denied | PASS | https://webshop.example.com/alcohol |  |  |
| 4 | Leave age empty or enter text | Proper error message | Same error message shown | FAIL | https://webshop.example.com/alcohol |  | https://github.com/abdelwahhab-hamadi/masterschool-QA-homeworks/issues/4 |


## FEATURE 3 – SHIPPING COST

### Test Case 5: Free shipping applied when total ≥ 20€

| Step# | Action | Expected Result | Actual Result | Status (PASS/FAIL) | URL | Evidence | Link to Issue |
|------:|--------|-----------------|--------------|--------------------|-----|----------|--------------|
| 1 | Open webshop home page | Home page opens |  |  | https://webshop.example.com |  |  |
| 2 | Add product to cart | Product added |  |  | https://webshop.example.com/product/123 |  |  |
| 3 | Go to cart page | Cart page opens |  |  | https://webshop.example.com/cart |  |  |
| 4 | Verify total ≥ 20€ | Total correct |  |  | https://webshop.example.com/cart |  |  |
| 5 | Check shipping cost | Free shipping applied | Free shipping applied | PASS | https://webshop.example.com/cart |  |  |


### Test Case 6: Shipping fee does not return when total drops below 20€ (Bug)

| Step# | Action | Expected Result | Actual Result | Status (PASS/FAIL) | URL | Evidence | Link to Issue |
|------:|--------|-----------------|--------------|--------------------|-----|----------|--------------|
| 1 | Add items until total ≥ 20€ | Free shipping applied |  |  | https://webshop.example.com/cart |  |  |
| 2 | Remove item from cart | Total < 20€ |  |  | https://webshop.example.com/cart |  |  |
| 3 | Check shipping cost | Shipping fee added | Shipping still free | FAIL | https://webshop.example.com/cart |  | https://github.com/abdelwahhab-hamadi/masterschool-QA-homeworks/issues/3 |
| 4 | Refresh cart page | Shipping fee persists | Shipping still free | FAIL | https://webshop.example.com/cart |  | https://github.com/abdelwahhab-hamadi/masterschool-QA-homeworks/issues/3 |
