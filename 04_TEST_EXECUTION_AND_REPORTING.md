# Scenario 1: Successful Login

As a user of MarketMate, I want to log in successfully so I can access my account.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|------|--------|------------------|--------|------|----------------|
| 1 | Go to the login page | Login page loads correctly | OK | https://grocerymate.masterschool.com/login | |
| 2 | Enter valid email and password | Fields accept the input | OK | | |
| 3 | Click “Login” | User is redirected to the homepage | OK | https://grocerymate.masterschool.com/ | |
| 4 | Verify login success | User can see account menu and products page | OK | | |

### Screenshots
- Screenshot 1: Login form
- <img width="1417" height="620" alt="Screenshot 2025-12-09 at 4 00 58 PM" src="https://github.com/user-attachments/assets/6938ea33-e291-4235-a36a-bf4aec53e2a7" />

- Screenshot 2: Logged-in homepage

- <img width="1426" height="628" alt="Screenshot 2025-12-09 at 4 01 35 PM" src="https://github.com/user-attachments/assets/65c3d47e-cb2c-4084-91be-bc85fc8bb8e3" />


- # Scenario 2: Add Review – Submit Rating + Comment

As a user of MarketMate, I want to submit a review containing a rating and a comment on a product page.

| Step# | Action | Expected outcome | OK/NOK | URL | Link to issue |
|------|---------|------------------|--------|------|----------------|
| 1 | Open a purchased product page | Review section is visible | OK | https://grocerymate.masterschool.com/product/XYZ | |
| 2 | Click “Add Review” | Review modal appears | OK | | |
| 3 | Write comment + select rating | Form accepts valid input | OK | | |
| 4 | Click “Submit” | Review should appear immediately (rating + comment) | NOK | | [https://github.com/…/issues/1](https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/1) |
| 5 | Refresh the page | Comment still not visible (bug) | NOK | | [https://github.com/…/issues/1](https://github.com/abdelwahahb-hamadi/masterschool-QA-homeworks/issues/1) |

### Screenshots
- Screenshot: Add Review modal before submitting
- <img width="1284" height="661" alt="Screenshot 2025-12-09 at 2 56 01 PM" src="https://github.com/user-attachments/assets/1f2f287d-ea61-42c7-8da6-d8a939cca2e9" />


- Screenshot: Rating appears but comment missing
- <img width="1387" height="465" alt="Screenshot 2025-12-09 at 2 57 46 PM" src="https://github.com/user-attachments/assets/33aa52e3-63e6-4d6d-b6a6-9ff98a274856" />
 
