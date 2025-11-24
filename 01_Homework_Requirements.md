# Requirements – Market Mate Webshop

## The Software
Market Mate is an online grocery webshop with the following existing functionalities:

- Register and login functionality  
- Searching for products, sorting by price, and browsing product categories  
- Add products to favorites  
- Add products to basket  
- Checkout process: billing details, entering information in a form, choosing payment method, and calculating total price  

You will test the newly developed features listed below.

---

# New Features

---

## 1. Product Rating System

### Vague Requirement
Users should be able to rate products using a 5-star rating system and optionally add written feedback.

### Questions
1. Do users need to be logged in to submit a rating, or can guests also rate products?  
2. Can users edit or delete their rating after submission?  
3. Are ratings limited to whole stars (1–5), or can half-star values be used?  

### Detailed Requirement
- Only logged-in users can submit ratings.  
- Ratings must be whole numbers from **1 to 5**, no half-stars allowed.  
- Each user can submit only **one rating per product**, but is allowed to **edit or delete** it.  
- Optional written feedback can be added and must be saved and displayed along with the rating.

---

## 2. Age Verification for Alcoholic Products

### Vague Requirement
Alcoholic products require age verification before users can view or purchase them.

### Questions
1. Should the age verification modal appear only when entering the Alcohol category, or also when searching for alcoholic items?  
2. If the user is under 18, should they be blocked from viewing alcoholic items entirely or only restricted from purchasing?  
3. Should there be a second age check during checkout if the basket contains alcoholic products?  

### Detailed Requirement
- Users must confirm that they are **18 or older** before accessing alcoholic products.  
- If the user is under 18, they must be blocked from **both viewing and purchasing** alcoholic products.  
- The age verification must trigger whenever alcoholic items appear (category page, search results, product page).  

---

## 3. Shipping Cost Changes

### Vague Requirement
Orders above a certain amount get free shipping. Orders below that amount pay a shipping fee.

### Questions
1. What is the exact amount needed to qualify for free shipping?  
2. Is the calculation based on the final total after discounts?  
3. What happens if a return reduces the total below the free-shipping threshold?

### Detailed Requirement
- Free shipping applies when the final amount after discounts is **20€ or more**.  
- Orders below 20€ must have a shipping fee added.  
- If a return reduces the order total below 20€, the system must charge shipping.
