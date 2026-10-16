# Financial-Data-API-CI-CD-Pipeline-
# Financial Transaction Service: Unit Testing, Manual Testing & CI/CD

A robust financial data validation and processing application designed to bridge business rules with software development lifecycle (SDLC) best practices. This project demonstrates automated unit testing, manual test execution, bug tracking, input validation hardening, and continuous integration (CI) via GitHub Actions.

---

## 🚀 Key Features & Responsibilities Addressed
- **Schema & Input Validation (Pydantic):** Ensures strict formatting for financial transactions, including mandatory positive amounts, non-blank ID/category restrictions, and normalized 3-letter uppercase currency codes.
- **Business Logic Enforcement:** Automates automated transaction volume limits (rejection above $100,000) and handles database integrity constraints (e.g., duplicate transaction ID prevention).
- **Manual & Automated Testing Rigor:** Features a comprehensive suite of automated tests (`pytest`) paired with 17 structured manual test cases that isolate real-world data input defects.
- **Continuous Integration (CI):** Implements a GitHub Actions workflow (`ci.yml`) to ensure automated build verification and code coverage reporting on every code push and pull request.

---

## 📂 Project Architecture
```text
financial-data-service/
│
├── app/
│   ├── __init__.py           # Package initialization
│   ├── models.py             # Pydantic data schemas & custom validators
│   ├── database.py           # SQLite storage layer & account summarization
│   └── service.py            # Business rule layer (limits & validation execution)
│
├── tests/
│   ├── test_service.py       # Automated unit tests for core services
│   └── test_validation.py    # Regression tests for input-validation defects
│
├── manual_tests/
│   └── run_manual_cases.py   # Script running 17 manual test scenarios (Expected vs. Actual)
│
├── .github/
│   └── workflows/
│       └── ci.yml            # CI/CD pipeline automation configuration
│
├── requirements.txt          # Project dependencies
└── README.md                 # Project documentation



---

# Part 2: Step-by-Step Process Based on the Deloitte BTA Job Description

The Deloitte Global Employer Services Technology Center JD emphasizes **technology operations, legislation-to-technology alignment, manual/automated testing, research, day-to-day application support, and process efficiency via AI tools**[cite: 1]. 

To align your project work and interview preparation directly with this role, follow this step-by-step roadmap:

### Step 1: Execute and Master Manual Testing (Aligns with *"Perform manual testing using Deloitte applications and Excel"*[cite: 1])
* **What to do:** Run the manual testing script (`python manual_tests/run_manual_cases.py before_fix`) found in your project cells[cite: 2]. 
* **The Action:** Review the 17 output scenarios. Note why scenarios like TC10 (Empty ID) or TC11 (Lowercase currency) initially fail[cite: 2]. Build a mental or physical bug log (Title, Steps to Reproduce, Expected vs. Actual Result, Severity) just as you would when testing enterprise tax/employer services software.

### Step 2: Implement Bug Fixes & Regression Testing (Aligns with *"Strong analytical and problem-solving skills"*[cite: 1])
* **What to do:** Apply the code update for `app/models.py` (introducing Pydantic `@field_validator` hooks)[cite: 2].
* **The Action:** Add regression tests in `tests/test_validation.py` to ensure that those specific bugs can never re-enter the codebase[cite: 2]. Re-run the manual script (`after_fix`) to confirm all 17 cases turn green (*Pass*)[cite: 2].

### Step 3: Package, Push to GitHub, and Monitor CI/CD (Aligns with *"Ability to deliver on time"* & *"Willingness to work independently"*[cite: 1])
* **What to do:** Download the generated project ZIP file, unpack it on your local machine, and initialize a new public GitHub repository named `financial-data-service`[cite: 2].
* **The Action:** Upload all files—ensuring the hidden `.github/workflows/ci.yml` folder is properly included[cite: 2]. Go to your repository's **Actions** tab on GitHub and confirm that the automated testing pipeline executes successfully with a green checkmark[cite: 2].

### Step 4: Leverage AI Tools for Documentation & Research (Aligns with *"Use AI tools to improve research, documentation, and problem-solving efficiency"*[cite: 1])
* **What to do:** Use AI tools (like ChatGPT or Claude) to analyze your test coverage logs, optimize code comments, or draft release notes. 
* **The Action:** Be ready to explain in an interview how you use AI to accelerate your workflow, write structured documentation, or troubleshoot code blocks rapidly.

### Step 5: Translate Project Experience into Interview Talking Points (Aligns with *"Excellent oral and written communication skills"* and client service orientation[cite: 1])
* **What to do:** Prepare to speak about this project using the **STAR method** (Situation, Task, Action, Result) during interviews:
  * *Situation:* Financial applications require rigorous compliance and zero tolerance for malformed data inputs (much like global employer tax and legislative rules).
  * *Task:* Identify structural gaps where automated tests passed, but user-facing manual test cases failed.
  * *Action:* Executed manual test scripts, documented input-validation edge cases, upgraded the Pydantic schema validator, and established a CI pipeline.
  * *Result:* Achieved 100% test pass rates, fixed 4 core data-integrity defects, and automated quality checks through GitHub Actions.
  
