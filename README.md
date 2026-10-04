# SQA Day 2 & 3 - Testing HisabDo

This repository contains my Day 2 and Day 3 SQA internship work at XICTEK Systems. I tested the HisabDo web application, a digital khata/ledger application for shopkeepers.

Day 1: Basic functional testing
Separate repository: https://github.com/Ramna-Raheem/SQA-Day-1-Testing
Day 2: Additional functional testing, UI/UX checks, and mobile view testing
Day 3: Boundary and negative testing, re-testing of Day 1 bugs, and API checks

What's in this repo

`Ramna Raheem HisabDo QA Report Day 2&3.xlsx` contains four sheets:

1. Test Cases - Day 2 and Day 3 test cases
2. Bug Reports - All 8 identified bugs and Day 3 re-test results for BUG001-003
3. API Checks - API checks using Chrome DevTools and Postman
4. Summary - Test results, bug severity, and key findings

What I Tested:

Registration, login, logout, Guest Mode, and Demo Account
Add Customer, Add Income, and Add Expense
Search, filters, delete customer, ledger, navigation, Settings, and Reports
Mobile view
Input validation for empty fields, negative numbers, zero, special characters, long text, and large numbers
Duplicate entries
Re-testing of the 3 Day 1 bugs
API requests using Chrome DevTools Network tab and Postman

Testing Results:

Days 1-3

30 test cases: 20 Passed, 8 Failed, 2 Blocked
8 bugs identified: 3 High, 3 Medium, 2 Low
All 3 Day 1 bugs were still reproducible on Day 3

Key Findings:

Add Customer, Add Income, and Add Expense failed on registered accounts. The forms were submitted, but the data was not saved and no clear error message was displayed. The same actions worked in Demo Account and Guest Mode.

During API testing, the requests for these three actions returned **400 Bad Request** from the Supabase backend. Further investigation of the request payload and API response is required to identify the exact cause.

Several input validation issues were also found. The phone number accepts letters, amount fields accept zero and negative values, the name field accepts special characters, and duplicate customers can be added.

Other tested features, including navigation, mobile layout, search, filters, delete, ledger, login/logout, Guest Mode, Demo Account, and Reports, worked as expected during testing.

Recommendation:

Investigate the API requests for Add Customer, Add Income, and Add Expense first because these issues affect important data-entry functions for registered accounts.

Input validation should also be improved for phone numbers, amounts, names, and duplicate customer entries.

Tools Used:

Google Sheets
Chrome DevTools
Postman
GitHub
Google Drive for browser screen recordings
