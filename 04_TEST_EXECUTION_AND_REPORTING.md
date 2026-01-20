# TEST EXECUTION & REPORTING – Market Mate Webshop

---

## Feature 1: Product Rating System

### Test Case 1: Submit rating with minimum allowed value (1 star)
| Step# | Action | Expected Result | Actual Result | Status (PASS/FAIL) | URL | Evidence | Link to Issue |
|------:|--------|-----------------|--------------|--------------------|-----|----------|--------------|
| 1 | Login to the webshop | User is logged in |  |  |  |  |  |
| 2 | Open a purchased product page | Product page opens |  |  |  |  |  |
| 3 | Click **Add Review** | Review form/modal opens |  |  |  |  |  |
| 4 | Select **1 star** | 1 star is selected |  |  |  |  |  |
| 5 | Click **Submit** | Rating is saved and displayed | Rating saved and displayed | PASS |  |  |  |

---

### Test Case 2: Submit rating without selecting stars (rating required)
| Step# | Action | Expected Result | Actual Result | Status (PASS/FAIL) | URL | Evidence | Link to Issue |
|------:|--------|-----------------|--------------|--------------------|-----|----------|--------------|
| 1 | Login to the webshop | User is logged in |  |  |  |  |  |
| 2 | Open a purchased product page | Product page opens |  |  |  |  |  |
| 3 | Click **Add Review** | Review form/modal opens |  |  |  |  |  |
| 4 | Leave stars empty and click **Submit** | Validation message appears (rating required) | Shows “Invalid” / rating required | PASS |  |  |  |

---

### Test Case 3: Submit rating + comment (comment should appear immediately)
| Step# | Action | Expected Result | Actual Result | Status (PASS/FAIL) | URL | Evidence | Link to Issue |
|------:|--------|-----------------|--------------|--------------------|-----|----------|--------------|
| 1 | Login to the webshop | User is logged in |  |  |  |  |  |
| 2 | Open a purchased product page | Product page opens |  |  |  |  |  |
| 3 | Click **Add Review** | Review form/modal opens |  |  |  |  |  |
| 4 | Select stars (e.g., 5) and type a comment | Input accepted |  |  |  |  |  |
| 5 | Click **Submit** | Stars + comment appear under the product | Only stars appear, comment is missing | FAIL |  |  |  |

---

## Feature 2: Age Verification for Alcoholic Products

### Test Case 1: Enter age exactly 18 (access allowed)
| Step# | Action | Expected Result | Actual Result | Status (PASS/FAIL) | URL | Evidence | Link to Issue |
|------:|--------|-----------------|--------------|--------------------|-----|----------|--------------|
| 1 | Clear cookies/session to reset age verification | Age modal appears again when needed |  |  |  |  |  |
| 2 | Navigate to Alcohol category | Age verification modal appears |  |  |  |  |  |
| 3 | Enter DOB that makes user **exactly 18** | Input accepted |  |  |  |  |  |
| 4 | Confirm / submit age | Alcohol category becomes accessible | Access allowed | PASS |  |  |  |

---

### Test Case 2: Enter age just below 18 (17) (access denied)
| Step# | Action | Expected Result | Actual Result | Status (PASS/FAIL) | URL | Evidence | Link to Issue |
|------:|--------|-----------------|--------------|--------------------|-----|----------|--------------|
| 1 | Clear cookies/session to reset age verification | Age modal appears again |  |  |  |  |  |
| 2 | Navigate to Alcohol category | Age verification modal appears |  |  |  |  |  |
| 3 | Enter DOB that makes user **17** | Input accepted |  |  |  |  |  |
| 4 | Confirm / submit age | Access denied (blocked from alcohol products) | Access denied / “No product found” | PASS |  |  |  |

---

### Test Case 3: Invalid age input (empty or text) should show validation message
| Step# | Action | Expected Result | Actual Result | Status (PASS/FAIL) | URL | Evidence | Link to Issue |
|------:|--------|-----------------|--------------|--------------------|-----|----------|--------------|
| 1 | Clear cookies/session to reset age verification | Age modal appears again |  |  |  |  |  |
| 2 | Navigate to Alcohol category | Age verification modal appears |  |  |  |  |  |
| 3 | Leave DOB empty OR enter text like “abc” | Validation error specific to invalid input | Same generic message shown for all cases | FAIL |  |  |  |

---

## Feature 3: Shipping Cost Changes (Threshold = 20€)

### Test Case 1: Cart total exactly 20.00€ (free shipping)
| Step# | Action | Expected Result | Actual Result | Status (PASS/FAIL) | URL | Evidence | Link to Issue |
|------:|--------|-----------------|--------------|--------------------|-----|----------|--------------|
| 1 | Add items until total becomes **20.00€** | Total updates correctly |  |  |  |  |  |
| 2 | Open cart/checkout summary | Shipping becomes free | Shipping is free | PASS |  |  |  |

---

### Test Case 2: Cart total just below 20€ (19.99€) (shipping fee applied)
| Step# | Action | Expected Result | Actual Result | Status (PASS/FAIL) | URL | Evidence | Link to Issue |
|------:|--------|-----------------|--------------|--------------------|-----|----------|--------------|
| 1 | Add items until total becomes **19.99€** | Total updates correctly |  |  |  |  |  |
| 2 | Open cart/checkout summary | Shipping fee is applied | Shipping fee applied | PASS |  |  |  |

---

### Test Case 3: Remove items (from >=20€ to <20€) should re-apply shipping fee
| Step# | Action | Expected Result | Actual Result | Status (PASS/FAIL) | URL | Evidence | Link to Issue |
|------:|--------|-----------------|--------------|--------------------|-----|----------|--------------|
| 1 | Add items until total becomes **>= 20€** | Free shipping is applied |  |  |  |  |  |
| 2 | Remove items until total becomes **< 20€** | Shipping fee should appear again | Shipping fee does NOT return | FAIL |  |  |  |
