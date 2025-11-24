# Requirements – Market Mate Webshop

## The software
Market Mate is an online grocery webshop with the following existing functionalities:

- Register and login functionality  
- Searching for products, sorting on price, categories of products  
- Add products to favorites  
- Add products to basket  
- Check-out process: billing and sending information in a form, choose payment method, and calculate total price  

You are going to test the newly developed features. The new features are written below.

---

# New Features

## 1. Product Rating System

### Vague Requirement:
Users should be able to rate products with a 5-star system and have the option to add written feedback.

### Questions:
1. Do users need to be logged in to rate a product, or can guests also submit ratings?  
2. Can users edit or delete their rating after submitting it?  
3. Are ratings limited to whole stars (1–5), or can half-star ratings be used?  

### Detailed Requirement:
Users must be logged in to submit a rating. Ratings must be whole numbers from 1 to 5.  
Each user can submit only one rating per product, but they may edit or delete it.  
Optional written feedback can be added and must be saved together with the rating.

---

## 2. Age Verification for Alcoholic Products

### Vague Requirement:
Alcoholic products require age verification before users are allowed to view or purchase them.

### Questions:
1. Should the age verification popup appear only when entering the Alcohol category, or also when searching for alcoholic products?  
2. If a user is under 18, should they be blocked from viewing the category entirely or only from purchasing?  
3. Should there be a second age check during checkout if the cart contains alcoholic products?  

### Detailed Requirement:
If the user is under 18, they must be prevented from viewing or purchasing alcoholic products.  

---

## 3. Shipping Cost Changes

### Vague Requirement:
Orders above a specific amount should receive free shipping. Orders below this threshold should incur a shipping fee.

### Questions:
1. What is the minimum order amount required to qualify for free shipping?  
2. Should the free-shipping threshold be calculated before tax or after discounts are applied?  
3. If a product is returned and the order total drops below the threshold, should the shipping cost be charged retroactively?  

### Detailed Requirement:
Free shipping applies only when the final payable amount (after discounts) is equal to or above the defined threshold.  
