# TEST CASE DESIGN – MARKET MATE

---

## 1. PRODUCT RATING SYSTEM

**Test Design Techniques:**
- Boundary Value Analysis (BVA)
- Equivalence Partitioning (EP)
- Error Guessing
- Use Case Testing

---

### TEST CASES

#### 1. Boundary Value Analysis (BVA)

- **TC-RATING-01 – Submit rating with minimum allowed value**  
  **Input:** Rating = 1  
  **Expected Outcome:** Rating is submitted successfully.

- **TC-RATING-02 – Submit rating with maximum allowed value**  
  **Input:** Rating = 5  
  **Expected Outcome:** Rating is submitted successfully.

---

#### 2. Equivalence Partitioning (EP)

- **TC-RATING-03 – Submit rating below valid range**  
  **Input:** Rating = 0  
  **Expected Outcome:** Error message “Invalid rating value.”

- **TC-RATING-04 – Submit rating above valid range**  
  **Input:** Rating = 6  
  **Expected Outcome:** Error message “Invalid rating value.”

---

#### 3. Error Guessing

- **TC-RATING-05 – Submit rating without selecting stars**  
  **Input:** Rating field empty  
  **Expected Outcome:** Error message “Rating is required.”

- **TC-RATING-06 – Submit rating using invalid characters**  
  **Input:** Rating = “five”  
  **Expected Outcome:** Error message “Invalid rating format.”

---

#### 4. Use Case Testing

- **TC-RATING-07 – Submit rating with a written comment**  
  **Input:** Rating = 4, Comment = “Very good product!”  
  **Expected Outcome:** Rating and comment are saved and displayed under the product.

- **TC-RATING-08 – Verify average rating updates correctly**  
  **Input:** Submit a new rating for a product that already has ratings  
  **Expected Outcome:** Average rating is recalculated and displayed correctly.

---

## 2. AGE VERIFICATION FOR ALCOHOLIC PRODUCTS

**Test Design Techniques:**
- Boundary Value Analysis (BVA)
- Equivalence Partitioning (EP)
- Error Guessing
- Use Case Testing

---

### TEST CASES

#### 1. Boundary Value Analysis (BVA)

- **TC-AGE-01 – Age exactly 18**  
  **Input:** Age = 18  
  **Expected Outcome:** Access allowed.

- **TC-AGE-02 – Age just below 18**  
  **Input:** Age = 17  
  **Expected Outcome:** Access denied, message “You must be 18+.”

---

#### 2. Equivalence Partitioning (EP)

- **TC-AGE-03 – Age group below 18**  
  **Input:** Age = 15  
  **Expected Outcome:** Access denied.

- **TC-AGE-04 – Age group above 18**  
  **Input:** Age = 25  
  **Expected Outcome:** Access granted.

---

#### 3. Error Guessing

- **TC-AGE-05 – Age field empty**  
  **Input:** “”  
  **Expected Outcome:** Error message “Age is required.”

- **TC-AGE-06 – Invalid age format**  
  **Input:** Age = “abc”  
  **Expected Outcome:** Error message “Invalid age format.”

---

#### 4. Use Case Testing

- **TC-AGE-07 – Age modal appears before accessing Alcohol section**  
  **Input:** Navigate to Alcohol category  
  **Expected Outcome:** Age verification modal appears.

- **TC-AGE-08 – Block access after incorrect age entry**  
  **Input:** Age = 16  
  **Expected Outcome:** User remains blocked from the Alcohol category.

---

## 3. SHIPPING COST CHANGES

**Rule:**
- Orders ≥ 20€ → Free shipping  
- Orders < 20€ → Shipping fee applied  

**Test Design Techniques:**
- Boundary Value Analysis (BVA)
- Equivalence Partitioning (EP)
- Error Guessing
- Use Case Testing

---

### TEST CASES

#### 1. Boundary Value Analysis (BVA)

- **TC-SHIP-01 – Order total exactly at free-shipping threshold**  
  **Input:** Cart total = 20.00€  
  **Expected Outcome:** Free shipping is applied.

- **TC-SHIP-02 – Order total just below threshold**  
  **Input:** Cart total = 19.99€  
  **Expected Outcome:** Shipping fee is added.

---

#### 2. Equivalence Partitioning (EP)

- **TC-SHIP-03 – Valid free-shipping partition**  
  **Input:** Cart total = 35€  
  **Expected Outcome:** Free shipping is applied.

- **TC-SHIP-04 – Valid shipping-fee partition**  
  **Input:** Cart total = 10€  
  **Expected Outcome:** Shipping fee is added.

---

#### 3. Error Guessing

- **TC-SHIP-05 – Negative cart total**  
  **Input:** -5€  
  **Expected Outcome:** Error “Invalid cart total.”

- **TC-SHIP-06 – Non-numeric cart total**  
  **Input:** “abc”  
  **Expected Outcome:** Error “Invalid amount format.”

- **TC-SHIP-07 – Cart total missing**  
  **Input:** “”  
  **Expected Outcome:** Error “Cart total is required.”

---

#### 4. Use Case Testing

- **TC-SHIP-08 – Shipping fee updates after removing an item**  
  **Input:** Start with total ≥ 20€, remove an item so total becomes < 20€  
  **Expected Outcome:** Shipping fee is added automatically.

- **TC-SHIP-09 – Shipping becomes free after adding items**  
  **Input:** Start with total < 20€, add items so total becomes ≥ 20€  
  **Expected Outcome:** Free shipping is applied.

---

## 4. Test Cases Selected for Automation

According to the assignment, the student must indicate which test case would be automated and why.

- **TC-RATING-01 (Submit rating with minimum allowed value)**  
  Reason: Stable, repeatable scenario that verifies the core rating flow. Good candidate for regression automation.

- **TC-AGE-01 (Age exactly 18)**  
  Reason: Critical boundary case for legal age; automating it ensures no regression in age-check logic.

- **TC-SHIP-01 (Order total exactly at free-shipping threshold)**  
  Reason: Important business rule; automating this BVA case ensures that free-shipping logic always behaves correctly after code changes.
