🧪 Benefits API Automation Framework
📌 Overview

Automated API testing framework developed to validate the Employees & Benefits module, ensuring business rules, financial calculations, and CRUD operations behave correctly.

This project demonstrates professional-level API automation using:

Postman

Newman (CLI execution)

HTML reporting

Deterministic test flow

Business rule validation

Boundary testing

End-to-end CRUD coverage

🎯 Objective

Validate that an employer can:

Add employees

Calculate benefit costs correctly

Edit employee data

Delete employees

See accurate results reflected in the system

All validations are automated and reproducible via CLI execution.

🏗 Architecture & Test Design

The suite is designed to be:

Deterministic

Independent

Self-cleaning

Free of hardcoded values

Execution-ready for CI/CD

🔁 Execution Flow (Collection Runner / Newman)

POST – Create Employee

GET by ID – Validate persistence

GET All – Validate dashboard visibility

PUT – Update employee

GET by ID – Validate update persistence

DELETE – Remove employee

GET by ID (Negative) – Confirm deletion

GET All – Validate record count decrement

This ensures full CRUD coverage and data integrity validation.

💰 Business Rules Validated
Assumptions

$2000 gross per paycheck

26 paychecks per year

$1000 annual benefit cost per employee

$500 annual cost per dependent

Financial Validation Logic
Yearly Benefits = 1000 + (dependents * 500)
Benefits per Paycheck = Yearly Benefits / 26
Net = 2000 - Benefits per Paycheck

Assertions validate:

Gross is correct

Benefits are calculated correctly

Net < Gross

Benefits are never negative

Decimal precision tolerance handled

🧪 Scenarios Covered
✅ Add Employee

Data persistence

UUID validation

Ownership validation

Financial calculation accuracy

Dashboard visibility

✅ Edit Employee

Field update validation

Recalculated financial values

Persistence re-validation

✅ Delete Employee

Correct status code

Negative validation after deletion

Record count validation

✅ Boundary Testing

0 dependents

1 dependent

Multiple dependents

Maximum allowed dependents (32)

🔍 Technical Validations

Dynamic UUID capture

Collection variable management

No hardcoded IDs

Status code validation (200, 201, 404, etc.)

Response structure validation

Ownership validation

Negative scenario handling

Error-resilient JSON parsing

🛠 Tech Stack

Postman

Newman

newman-reporter-htmlextra

Node.js

⚙️ Installation & Execution
Install Dependencies
npm install -g newman
npm install -g newman-reporter-htmlextra
Run Tests
newman run Benefits_Automation.postman_collection.json
Generate HTML Report
newman run Benefits_Automation.postman_collection.json \
-r htmlextra \
--reporter-htmlextra-export report.html

Open report.html to view execution summary.
URL for open the report.html on Browser:
https://jesusqaenginner.github.io/Paylocity_Benefits_Dasboard-API_Automation-Postman/reports/report.html

📊 Sample Report Includes

Total requests executed

Pass/Fail breakdown

Detailed assertion logs

Response time metrics

Request/Response bodies

Visual execution summary

🚀 CI/CD Ready

The suite is prepared for:

GitHub Actions integration

Pipeline execution

Automated report generation

Version-controlled test execution

📈 What This Project Demonstrates

Real-world API automation

Business logic validation

Clean variable management

Robust test design

CLI execution outside Postman UI

Reporting for stakeholders

Automation discipline (no flaky tests)

👤 Author

Jesus Ricardo Hernandez Campos |
API Testing | Automation Strategy | CI/CD Ready Frameworks

🏆 Why This Matters

This project reflects production-level thinking:

Validates not just endpoints, but business rules.

Ensures financial correctness.

Prevents false positives.

Uses deterministic execution flow.

Ready for enterprise pipelines.
