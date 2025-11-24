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

- **Test Case: Submit rating with minimum allowed value**  
  **Input:** Rating = 1  
  **Expected Outcome:** Rating is submitted successfully.

- **Test Case: Submit rating with maximum allowed value**  
  **Input:** Rating = 5  
  **Expected Outcome:** Rating is submitted successfully.

---

#### 2. Equivalence Partitioning (EP)

- **Test Case: Submit rating below valid range**  
  **Input:** Rating = 0  
  **Expected Outcome:** Error message “Invalid rating value.”

- **Test Case: Submit rating above valid range**  
  **Input:** Rating = 6  
  **Expected Outcome:** Error message “Invalid rating value.”

---

#### 3. Error Guessing

- **Test Case: Submit rating without selecting stars**  
  **Input:** Rating field empty  
  **Expected Outcome:** Error message “Rating is required.”

- **Test Case: Submit rating using invalid characters**  
  **Input:** “five”  
  **Expected Outcome:** Error message “Invalid rating format.”

---

#### 4. Use Case Testing

- **Test Case: Submit rating with a written comment**  
  **Input:** Rating = 4, Comment = “Very good product!”  
  **Expected Outcome:** Rating and comment are saved and displayed under the product.

- **Test Case: Verify average rating updates correctly**  
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

- **Test Case: Age exactly 18**  
  **Input:** Age = 18  
  **Expected Outcome:** Access allowed.

- **Test Case: Age just below 18**  
  **Input:** Age = 17  
  **Expected Outcome:** Access denied, message “You must be 18+.”

---

#### 2. Equivalence Partitioning (EP)

- **Test Case: Age group below 18**  
  **Input:** Age = 15  
  **Expected Outcome:** Access denied.

- **Test Case: Age group above 18**  
  **Input:** Age = 25  
  **Expected Outcome:** Access granted.

---

#### 3. Error Guessing

- **Test Case: Age field empty**  
  **Input:** “”  
  **Expected Outcome:** Error message “Age is required.”

- **Test Case: Invalid age format**  
  **Input:** Age = “abc”  
  **Expected Outcome:** Error message “Invalid age format.”

---

#### 4. Use Case Testing

- **Test Case: Age modal appears before accessing Alcohol section**  
  **Input:** Navigate to Alcohol category  
  **Expected Outcome:** Age verification modal appears.

- **Test Case: Block access after incorrect age entry**  
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

- **Test Case: Order total exactly at free-shipping threshold**  
  **Input:** Cart total = 20.00€  
  **Expected Outcome:** Free shipping is applied.

- **Test Case: Order total just below threshold**  
  **Input:** Cart total = 19.99€  
  **Expected Outcome:** Shipping fee is added.

---

#### 2. Equivalence Partitioning (EP)

- **Test Case: Valid free-shipping partition**  
  **Input:** Cart total = 35€  
  **Expected Outcome:** Free shipping is applied.

- **Test Case: Valid shipping-fee partition**  
  **Input:** Cart total = 10€  
  **Expected Outcome:** Shipping fee is added.

---

#### 3. Error Guessing

- **Test Case: Negative cart total**  
  **Input:** -5€  
  **Expected Outcome:** Error “Invalid cart total.”

- **Test Case: Non-numeric cart total**  
  **Input:** “abc”  
  **Expected Outcome:** Error “Invalid amount format.”

- **Test Case: Cart total missing**  
  **Input:** “”  
  **Expected Outcome:** Error “Cart total is required.”

---

#### 4. Use Case Testing

- **Test Case: Shipping fee updates after removing an item**  
  **Input:** Start with total ≥ 20€, remove an item so total becomes < 20€  
  **Expected Outcome:** Shipping fee is added automatically.

- **Test Case: Shipping becomes free after adding items**  
  **Input:** Start with total < 20€, add items so total becomes ≥ 20€  
  **Expected Outcome:** Free shipping is applied.

---

## 4. Test Cases Selected for Automation

- **Test Case: Submit rating with minimum allowed value**  
  Reason: Stable, repeatable scenario that verifies core functionality.

- **Test Case: Age exactly 18**  
  Reason: Critical boundary case for legal verification.

- **Test Case: Order total exactly at free-shipping threshold**  
  Reason: Important business rule; suitable for regression automation.
