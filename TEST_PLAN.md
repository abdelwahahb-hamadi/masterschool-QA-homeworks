# TEST PLAN – Market Mate Webshop

---

## 1. Analyze the Product

### **Objective**
Ensure that the new features (Product Rating System, Age Verification for Alcoholic Products, Shipping Cost Changes) work correctly, integrate smoothly with existing webshop functionality, and do not affect the stability of the platform.

### **User Base**
- Regular customers buying groceries online  
- Guests browsing without accounts  
- Adults (18+) purchasing alcoholic products  

### **Hardware and Software Specifications**

#### **Hardware Requirements**
- PCs, laptops, smartphones, tablets  
- Minimum: 4GB RAM, 2GHz CPU  
- Standard Android & iOS devices

#### **Software Requirements**
- Operating Systems: Windows, macOS, Android, iOS  
- Browsers: Chrome, Safari, Firefox, Edge  
- Dependencies: Backend APIs, database, authentication service, payment gateway

### **Product Functionality**
**Existing functionality:**
- Registration & Login  
- Search & filtering  
- Add to Favorites  
- Add to Basket  
- Checkout (billing info + shipping info + payment + price calculation)

**New functionality to test:**
1. Product Rating System  
2. Age Verification for Alcoholic Products  
3. Shipping Cost Changes  

---

## 2. Design the Test Strategy

### **Scope of Testing**

#### **In Scope**
- All 3 new features  
- UI validation  
- Backend logic (ratings, age verification, shipping )  
- Cross-browser behavior  
- Regression on affected functionality  

#### **Out of Scope**
- Payment gateway integration  
- Mobile app (if exists)  
- Backend performance  
- Admin dashboard  

---

### **Type of Testing**
- Functional Testing  
- Validation Testing  
- Boundary Value Analysis (BVA)  
- Usability Testing  
- Regression Testing  
- Cross-browser Testing  

---

### **Risks and Issues**
- **Delays in development** → Mitigation: Add buffer days  
- **Lack of test data** → Mitigation: Create mock accounts & carts  
- **Resource unavailability** → Mitigation: Assign backup testers  

---

## 3. Define Test Objectives

### **Objectives**
- Verify product rating saves & updates correctly  
- Ensure under-18 users cannot access alcoholic products  
- Validate shipping cost logic and thresholds  
- Prevent regression in main webshop features  

### **Expected Outcomes**
- Ratings saved & reflected in average score  
- Age verification blocks minors  
- Shipping fees applied correctly  
- No major bugs remain  
- Smooth multi-browser behavior  

---

## 4. Define Test Criteria

### **Suspension Criteria**
- Blocking defects preventing execution  
- Test environment failure  

### **Exit Criteria**
- 100% test cases executed  
- ≥95% run rate  
- ≥90% pass rate  
- No Severity 1 or Severity 2 defects open  
- All critical issues resolved  
- UAT approved  

---

## 5. Resource Planning

### **Human Resources**
- QA Engineer  
- Test Manager  
- Developer  
- End User (UAT)  

### **Hardware**
- Laptops, PCs, mobile devices  

### **Software**
- Chrome, Firefox, Safari, Edge  
- GitHub, Selenium (future), Postman  

### **Infrastructure**
- Staging environment  
- Test data  

---

## 6. Plan Test Environment
- All testing will be executed in **staging (TEST)** environment.  
- Real devices + real browsers.  

**Environments:**
- DEV – development  
- TEST – QA testing  
- ACC – acceptance  
- PROD – production  

---

## 7. Schedule and Estimation

| Activity | Start | End | Environment | Responsible | Effort |
|---------|-------|------|-------------|--------------|--------|
| Test Planning | 12/02/2025 | 12/02/2025 | TEST | QA Engineer | 4h |
| Test Case Design | 12/02/2025 | 13/02/2025 | TEST | QA Engineer | 8h |
| System Testing | 13/02/2025 | 14/02/2025 | TEST | QA Engineer | 8h |
| Regression Testing | 14/02/2025 | 15/02/2025 | TEST | QA Engineer | 6h |
| UAT | 16/02/2025 | 17/02/2025 | ACC | End User | 4h |

---

## 8. Determine Test Deliverables
- Test Plan Document  
- Test Cases & Test Scripts  
- Defect Reports  
- Regression Test Suite  
- Test Summary Report  
- UAT Sign-off  

---
