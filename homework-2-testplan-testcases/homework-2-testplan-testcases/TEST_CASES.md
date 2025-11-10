# TEST CASES – Market Mate Webshop

---

## Feature 1: Product Rating System

**Test Case 1**  
**Objective:** Verify that a logged-in user can rate a product with stars.  
**Precondition:** User account exists and user is logged in.  
**Steps:**  
- Navigate to any product page.  
- Select a star rating (1–5).  
- Click “Submit”.  
**Expected Result:** Rating is saved and visible under the product.  
**Test Design Technique:** Positive Scenario.  
**Automatable:** Yes – can be automated using Selenium.

**Test Case 2**  
**Objective:** Verify that guest users cannot submit ratings.  
**Precondition:** User not logged in.  
**Steps:**  
- Open any product page.  
- Try to rate the product.  
**Expected Result:** System prompts the user to log in before submitting a rating.  
**Test Design Technique:** Negative Scenario.  
**Automatable:** Yes – basic UI automation possible.

**Test Case 3**  
**Objective:** Verify that ratings update the average score correctly.  
**Precondition:** Product already has ratings from multiple users.  
**Steps:**  
- Submit a new rating.  
**Expected Result:** Average rating value updates accordingly.  
**Test Design Technique:** Boundary/Calculation Validation.  
**Automatable:** Yes – can check values programmatically.

---

## Feature 2: Age Verification for Alcoholic Products

**Test Case 1**  
**Objective:** Verify that the age verification modal appears when entering the alcohol category.  
**Precondition:** User not yet verified.  
**Steps:**  
- Go to “Alcoholic Products” category.  
**Expected Result:** Age verification modal appears asking for confirmation.  
**Test Design Technique:** UI Validation.  
**Automatable:** Yes.

**Test Case 2**  
**Objective:** Verify that users under 18 cannot access the category.  
**Precondition:** User enters age below 18.  
**Steps:**  
- Enter age 17.  
- Click “Confirm”.  
**Expected Result:** Access is denied and user remains on the same page.  
**Test Design Technique:** Boundary Value (Age = 17).  
**Automatable:** Yes – edge case check.

**Test Case 3**  
**Objective:** Verify that the verification persists during the session.  
**Precondition:** User already verified as 18+.  
**Steps:**  
- Navigate to a non-alcoholic category, then back to Alcohol.  
**Expected Result:** User is not asked again within the same session.  
**Test Design Technique:** Session Persistence Check.  
**Automatable:** Possible but optional.

---

## Feature 3: Shipping Cost Changes

**Test Case 1**  
**Objective:** Verify free shipping applies when total exceeds threshold.  
**Precondition:** Free shipping threshold = 50€.  
**Steps:**  
- Add products totaling more than 50€.  
- Proceed to checkout.  
**Expected Result:** Shipping cost = 0€.  
**Test Design Technique:** Boundary Value (just above threshold).  
**Automatable:** Yes.

**Test Case 2**  
**Objective:** Verify shipping fee is applied when total below threshold.  
**Precondition:** Free shipping threshold = 50€.  
**Steps:**  
- Add products totaling less than 50€.  
- Proceed to checkout.  
**Expected Result:** Shipping cost added correctly.  
**Test Design Technique:** Boundary Value (just below threshold).  
**Automatable:** Yes.

**Test Case 3**  
**Objective:** Verify message “Spend X more for free shipping” appears when total is below threshold.  
**Precondition:** User has items worth less than 50€ in the basket.  
**Steps:**  
- View basket page.  
**Expected Result:** Message displays the remaining amount to reach free shipping.  
**Test Design Technique:** UI Validation.  
**Automatable:** Yes.
