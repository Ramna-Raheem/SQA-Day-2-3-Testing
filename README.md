# SQA-Day-2-3-Testing

## About This Project
This is my 3-day SQA internship task. I tested the HisabDo web app (app.hisabdo.app), a digital khata/ledger app for shopkeepers. Day 1 was basic functional testing, Day 2 covered more features and UI/UX, and Day 3 was boundary testing, regression, and some API testing.

## What's in This Repo
The spreadsheet (HisabDo_QA_Report_Day2-3.xlsx) has all test cases and bug reports, organized by day, plus a regression check and summary.

## What I Tested
Registration, login, logout
 Add Customer, Add Income, Add Expense (on regular accounts, Demo Account, and Guest Mode)
 Search, filters, delete, view ledger
 Navigation and mobile view
 Input validation  empty fields, negative numbers, special characters, long text
 Duplicate entries
 Regression testing of Day 1 bugs
 API testing with Chrome DevTools and Postman (bonus)

## Totals
30 test cases across 3 days
8 bugs documented
All 3 Day 1 bugs still reproducible when I re-tested on Day 3

## Key Findings

Add Customer, Add Income, and Add Expense all fail on regular/registered accounts  the form submits but nothing gets saved, no error shown. I re-tested this on Day 3 and it was still broken.

I used Chrome DevTools and Postman to check what was happening in the background, and found the API calls were returning 401 Unauthorized from the backend (Supabase). This points to a missing or broken API key/auth token for regular accounts probably the actual cause behind all three bugs, not three separate issues.

A few fields also accept bad input without any warning: phone numbers take letters, amount fields take negative numbers and zero, and the name field takes special characters.

Navigation, mobile layout, search, filters, delete, login/logout, Guest Mode, Demo Account, and Reports all worked fine.

## My Recommendation
Fix the authentication/API issue first it's blocking core functionality for real accounts. Right now the app only really works in Guest or Demo mode.
