# Test Execution Report – Market Mate Webshop

Below is the list of issues found while testing the new features (Age Verification, Product Rating, Shipping Cost Logic).  
The report is written in a simple and clear way based on real tests done on the website.

---

## Bug 1 – Comment does not show on first review
When adding a rating for the first time, only the stars are saved.  
The comment text is not displayed on the product page.

**Steps:**
1. Login.
2. Buy a product.
3. Add a rating + comment.
4. Submit.

**Expected:** Stars + comment should both appear.  
**Actual:** Only the stars show. Comment is missing.

---

## Bug 2 – Add Review and Edit Review have different rules
The “Add Review” modal has a 500-character limit and validation errors.  
But the “Edit Review” modal allows more than 500 characters with no error at all.

**Expected:** Same validation rules for Add and Edit.  
**Actual:** They behave differently.

---

## Bug 3 – Shipping fee does not return after cart drops below 20€
If the cart total reaches 20€ or more, shipping becomes free (correct).  
But if you remove items and the total goes below 20€, the shipping fee does not come back.

**Expected:** Shipping fee should appear again.  
**Actual:** Shipping stays free even under 20€.

---

## Bug 4 – Same age error message for all invalid inputs
The age verification popup shows the same message for every case:
- Empty age field  
- Invalid date format  
- Age below 18  
- Random text like “abc”

**Expected:** Different messages depending on the error.  
**Actual:** Always shows the under-age message.

---

## Bug 5 – Rating only possible after purchase
The website does not allow users to rate any product unless they have bought it first.  
This is not written in the requirements, so it might be missing clarification.

---

## Bug 6 – Long comments accepted only in Edit mode
The first Add Review does not accept more than 500 characters,  
but Edit Review accepts long text without limits.

**Expected:** Same behavior in both places.  
**Actual:** Different behavior.

---

## Bug 7 – Under-age warning appears even outside alcohol category
If the user is under 18, the warning message appears even when browsing normal products.  
This does not match the expected behavior (popup should only appear for alcoholic products).

---

## Test Summary
Most test cases were executed successfully, but several issues were found.  
Main problems are related to age validation, inconsistent review behavior, and shipping recalculation.
