
# 🧪 Benefits API Automation Framework

## 📌 Overview

Automated API testing framework developed to validate the Employees & Benefits module.

The objective is to ensure business rules, financial calculations, and CRUD operations behave correctly under deterministic execution conditions.

This project demonstrates professional API automation using:

- Postman  
- Newman CLI execution  
- HTML reporting  
- Business rule validation  
- Boundary testing  
- End-to-end CRUD workflow coverage  

---

## 🎯 Objective

Validate employer ability to:

- Add employees  
- Calculate benefit costs correctly  
- Edit employee data  
- Delete employees  
- Maintain data consistency across requests  

All tests are designed to be reproducible via CLI execution.

---

## 🏗 Architecture & Test Design Principles

The automation suite follows:

- Deterministic test execution  
- Independent request validation  
- No hardcoded identifiers  
- CI/CD pipeline readiness  
- Self-cleaning test behavior  

---

## 🔁 Execution Flow

The Collection Runner / Newman execution sequence is:

1. POST – Create Employee  
2. GET by ID – Validate persistence  
3. GET All – Validate dashboard visibility  
4. PUT – Update employee data  
5. GET by ID – Validate updates  
6. DELETE – Remove employee  
7. GET by ID – Confirm deletion (negative test)  
8. GET All – Validate record count integrity  

This ensures full CRUD lifecycle validation.

---

## 💰 Business Rules Assumptions

Financial model used during testing:

- Employee Gross Pay = $2000 per paycheck  
- 26 paychecks per year  
- Annual Employee Benefit Cost = $1000  
- Dependent Cost = $500 per dependent  

### Calculation Model

Yearly Benefits = 1000 + (Dependents × 500)
Benefits per Paycheck = Yearly Benefits ÷ 26
Net Paycheck = 2000 − Benefits per Paycheck


Assertions validate:

- Gross value correctness  
- Benefit calculation accuracy  
- Net < Gross condition  
- Non-negative benefit values  
- Decimal precision tolerance  

---

## 🧪 Test Coverage Scenarios

### ✅ Add Employee Validation

- Data persistence verification  
- UUID dynamic capture  
- Ownership validation  
- Financial calculation integrity  
- Dashboard visibility confirmation  

---

### ✅ Edit Employee Validation

- Field update correctness  
- Payroll preview recalculation  
- Persistence re-validation  

---

### ✅ Delete Employee Validation

- Correct HTTP response codes  
- Negative scenario verification  
- Record count validation  

---

### ✅ Boundary Testing

Dependent values tested:

| Dependents | Expected Behavior |
|---|---|
| 0 | Valid |
| 1 | Valid |
| 32 | Maximum allowed |
| >32 | Should be rejected |

---

## 🔍 Technical Validation Strategies

- Dynamic UUID handling  
- Collection variable storage  
- No hardcoded request identifiers  
- Status code verification (200, 201, 404, etc.)  
- Response schema integrity  
- Ownership validation  
- Error-safe JSON parsing  

---

## 🛠 Technology Stack

- Postman  
- Newman  
- newman-reporter-htmlextra  
- Node.js  

---

## ⚙️ Installation and Execution

### Install Dependencies

```bash
npm install -g newman
npm install -g newman-reporter-htmlextra
```

## Run Test Collection

newman run Benefits_Automation.postman_collection.json
Or you can download the Postman collection and imported it to your Postman and Run it.

## Generate HTML Report

newman run Benefits_Automation.postman_collection.json \
-r htmlextra \
--reporter-htmlextra-export report.html

## 📊 Report Features

### Execution report includes:

Total requests executed

Assertion pass/fail summary

Response metrics

Request and response bodies

Visual execution dashboard

## Report URL:

Last Run Report on GitHub Pages:
https://jesusqaenginner.github.io/Paylocity_Benefits_Dasboard-API_Automation-Postman/reports/report.html

## 🚀 CI/CD Readiness

The framework supports:

GitHub Actions integration

Pipeline execution automation

Version-controlled testing

Headless CLI execution

## 📈 Engineering Value Demonstrated

This project showcases:

Production-grade API automation

Business rule validation

Robust test design

CLI-based execution

Reporting for technical and business stakeholders

## 👤 Author

Jesus Ricardo Hernandez Campos

QA Automation Engineer

API Testing | Automation Strategy | CI/CD Awareness

## 🏆 Quality Engineering Philosophy

The primary objective is not only defect detection but risk mitigation, business logic validation, and reliability assurance.





