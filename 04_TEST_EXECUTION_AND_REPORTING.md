# TEST EXECUTION & REPORTING – Market Mate Webshop

This document contains:
- Test Environment
- Test Execution Results (PASS / FAIL)
- Actual Results
- Final Bug List

---

# 1. TEST ENVIRONMENT

- Device: MacBook Pro
- OS: macOS
- Browser: Google Chrome (latest)
- Application: https://grocerymate.masterschool.com/
- Environment: Production (Live website)
- User State: Logged-in user with completed purchase for rating tests

---

# 2. TEST EXECUTION RESULTS

## ================================
## FEATURE 1: PRODUCT RATING SYSTEM
## ================================

### ✔ TC1 – Submit rating = 1 (BVA)
**Expected:** Rating saved  
**Actual:** Rating saved successfully  
**Status:** PASS

---

### ✔ TC2 – Submit rating = 5 (BVA)
**Expected:** Rating saved  
**Actual:** Rating saved successfully  
**Status:** PASS

---

### ❌ TC3 – Add Review with comment (Use Case)
**Expected:** Rating + comment appear under product  
**Actual:** Rating saved BUT comment does NOT appear  
**Status:** FAIL  
**Bug:** Comment not saved on first review submission

---

### ✔ TC4 – Edit Review (Use Case)
**Expected:** Edit rating + comment works  
**Actual:** 
- Stars can be edited (1–5)  
- Comment shown after editing  
**Status:** PASS

---

### ✔ TC5 – Invalid rating values (EP)
Tested: 0, -1, 6, letters  
**Expected:** System rejects invalid inputs  
**Actual:** System rejects all invalid values correctly  
**Status:** PASS

---

### ✔ TC6 – Submit without stars (Error Guessing)
**Expected:** Error message  
**Actual:** “Invalid input for the field ‘Rating’”  
**Status:** PASS

---

### ❌ TC7 – Comment length = 500 (Boundary)
**Expected:** Accept & display  
**Actual:** Accepts, but **NOT displayed**  
**Status:** FAIL

---

### ❌ TC8 – Comment length > 500 (Boundary)
**Actual:**
- In ADD → rejected (correct)
- In EDIT → accepted (unexpected)  
**Status:** FAIL / INCONSISTENT BEHAVIOR

---

## FINAL RESULT (RATING):
✔ Logic works  
❌ Comment system broken on first review  
❌ Length validation inconsistent

---

## ================================
## FEATURE 2: AGE VERIFICATION
## ================================

### ✔ TC1 – Age = 18 (BVA)
**Expected:** Access allowed  
**Actual:** Access allowed and alcohol visible  
**Status:** PASS

---

### ✔/❌ TC2 – Age = 17 (BVA)
**Expected:** Block access + clear message  
**Actual:** Alcohol hidden BUT message shown is  
“Sorry, no product found.”  
→ Logic PASS / Message FAIL  
**Status:** PASS (logic) / FAIL (UX)

---

### ❌ TC3 – Empty age field
**Expected:** Validation error  
**Actual:** Modal closes without proper error  
**Status:** FAIL

---

### ❌ TC4 – Age = "abc" (Error Guessing)
**Expected:** “Invalid age format”  
**Actual:** Blocked but no proper error  
**Status:** FAIL

---

### ✔ TC5 – Does checkout ask age again?
**Actual:** No  
**Status:** PASS (because requirement does NOT mention second check)

---

### ❌ TC6 – Age popup appears on normal products
**Actual:** Popup appears even outside alcohol  
**Status:** FAIL (Requirement violation)

---

## FINAL RESULT (AGE):
✔ Logic correct  
❌ Messages incorrect  
❌ Popup appearing in wrong place  
❌ No validation messages

---

## ================================
## FEATURE 3: SHIPPING COST CHANGES
## ================================

### ✔ TC1 – Total = 19.99€ (BVA)
**Expected:** Shipping fee applied  
**Actual:** Shipping shows correctly  
**Status:** PASS

---

### ✔ TC2 – Total = 20€ (BVA)
**Expected:** Free shipping  
**Actual:** Free shipping applied  
**Status:** PASS

---

### ✔ TC3 – Total = 35€ (EP)
**Expected:** Free shipping  
**Actual:** Free  
**Status:** PASS

---

### ✔ TC4 – Total = 10€ (EP)
**Expected:** Shipping fee applied  
**Actual:** Shipping applies  
**Status:** PASS

---

### ❌ TC5 – Remove items → total drops below 20€ (Use Case)
**Expected:** Shipping fee should return  
**Actual:** Shipping stays FREE → major bug  
**Status:** FAIL

---

### ⚠ TC6 – Error Guessing
(Numbers typed manually not applicable due to UI design)  
Test case marked as N/A.

---

## FINAL RESULT (SHIPPING):
✔ Boundary correct  
✔ Threshold correct  
❌ Critical Bug: Free shipping stays active after removing items  
❌ Shipping does NOT re-apply below threshold

---

# 3. FINAL BUG LIST

## 🐞 BUG 1 – Comment not saved on first review submission
- Rating saved, comment disappears  
- Happens only on ADD, not EDIT  
**Severity:** HIGH

## 🐞 BUG 2 – Comment = 500 chars accepted but not shown
**Severity:** MEDIUM

## 🐞 BUG 3 – Comment > 500 accepted in EDIT
**Severity:** MEDIUM

## 🐞 BUG 4 – Age verification popup shows on non-alcohol products
**Severity:** HIGH

## 🐞 BUG 5 – Underage user sees “No products found” instead of age warning
**Severity:** MEDIUM

## 🐞 BUG 6 – Empty age field accepted without error
**Severity:** HIGH

## 🐞 BUG 7 – Invalid age format “abc” not handled properly
**Severity:** MEDIUM

## 🐞 BUG 8 – Shipping fee does NOT return when total drops below threshold
**Severity:** CRITICAL

---

# ✔ END OF REPORT
