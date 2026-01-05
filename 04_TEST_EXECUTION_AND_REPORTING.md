# Test Execution – MarketMate 

This document contains executed test scenarios for the 3 new features:
1) Product Rating System
2) Age Verification for Alcoholic Products
3) Shipping Cost Changes

---

# Scenario 1: Product Rating – Submit Rating + Comment

As a user of MarketMate, I want to submit a review (rating + written comment) for a product.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|------|--------|------------------|--------|-----|---------------|
| 1 | Login and open a product page that allows reviews | Review section is visible | OK | https://grocerymate.masterschool.com/product/XYZ | |
| 2 | Click “Add Review” | Review modal appears | OK |  | |
| 3 | Select a rating (e.g., 5 stars) and write a short comment | Form accepts valid input | OK |  | |
| 4 | Click “Submit” | Review appears immediately (rating + comment) | NOK |  | https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/1 |

---

# Scenario 2: Age Verification – Access Alcohol Category

As a user of MarketMate, I must confirm I am 18+ before accessing alcoholic products.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|------|--------|------------------|--------|-----|---------------|
| 1 | Navigate to Alcohol category | Age verification modal appears | OK | https://grocerymate.masterschool.com/alcohol | |
| 2 | Enter a birthdate that makes the user 18+ (e.g., 20-12-1988) and confirm | User can access alcoholic products | OK |  | |
| 3 | Clear cookies / reset and enter a birthdate that makes the user under 18 (e.g., 20-12-2014) | User is blocked from alcohol products | OK |  | |

---

# Scenario 3: Shipping Cost – Free Shipping Threshold (20€)

As a user of MarketMate, shipping should be free for orders ≥ 20€, and a fee should apply for orders < 20€.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|------|--------|------------------|--------|-----|---------------|
| 1 | Add items to cart until total is 19.99€ | Shipping fee is applied | OK | https://grocerymate.masterschool.com/cart | |
| 2 | Add one more item so total becomes 20.00€ or more | Shipping becomes free | OK |  | |
| 3 | Remove items so total drops below 20€ again | Shipping fee should be applied again | NOK |  | (add issue link if you created one) |
