# PL/SQL GOTO Statements and Functions

Course: Database Development with PL/SQL (INSY 8311)
Instructor: Eric Maniraguha
Assignment: Individual Assignment III
Student: DIVIN IZERE
Student ID: 28979
Group: I
Database: Oracle (SQL Developer)

---

 1. Introduction

This repository contains my solution for Individual Assignment III. The assignment focuses on PL/SQL `GOTO` statements, labels, stored functions, exception handling, and using functions inside SQL queries.

The final part combines these concepts in a payroll validation function. The main goal was to understand how PL/SQL controls program flow and how reusable functions can be used to solve database-related problems.

2. Repository Structure

plsql-goto-functions-28979-DIVIN/'

├── README.md
├── .gitignore
├── 00_setup/create_tables.sql
├── 01_goto/
│   ├── A1_number_classifier.sql
│   ├── A2_salary_review.sql
│   ├── A3_illegal_goto.sql
│   └── A4_rewrite_no_goto.sql
├── 02_functions/
│   ├── B1_fn_annual_salary.sql
│   ├── B2_fn_years_of_service.sql
│   ├── B3_fn_calculate_tax.sql
│   ├── B4_fn_dept_name.sql
│   └── C1_fn_validate_payroll.sql
├── 03_tests/
│   ├── B5_functions_in_select.sql
│   ├── test_functions.sql
│   └── test_validate_payroll.sql
├── screenshots/
└── docs/REFLECTION.md
```

3. How to Run

Run the files in this order:

1. `00_setup/create_tables.sql`
2. Functions `B1` to `B4`
3. Function `C1`
4. GOTO programs `A1` to `A4`
5. Test files in `03_tests/`

Enable output before running:

/// sql

4. Main Concepts Covered

Part A - GOTO

The GOTO programs demonstrate:

* Using labels and `GOTO`
* Classifying numbers
* Reviewing salaries
* Illegal GOTO statements and `PLS-00375`
* Rewriting GOTO programs using `IF`, `CASE`, and `CONTINUE`

One important lesson is that a GOTO can move within the same block or outward, but it cannot jump **into** an inner block.

Part B - Functions

The assignment includes four functions:

| Function              | Purpose                     |
| --------------------- | --------------------------- |
| `fn_annual_salary`    | Calculates annual salary    |
| `fn_years_of_service` | Calculates years of service |
| `fn_calculate_tax`    | Calculates progressive tax  |
| `fn_dept_name`        | Returns the department name |

The functions also demonstrate exception handling, including `NO_DATA_FOUND` and `RAISE_APPLICATION_ERROR`.

Part C - Payroll Validation

`fn_validate_payroll` combines the concepts from the assignment.

It checks:

* Employee ID
* Employee existence
* Salary
* Department
* Hire date
* Tax

It returns either `VALID` or `INVALID: <reason>`.

5. Expected Results

| Employee | Result                  |
| -------- | ----------------------- |
| 101–106  | `VALID`                 |
| 107      | Invalid department      |
| 108      | Invalid salary          |
| 109      | Future hire date        |
| 999      | Employee does not exist |
| `NULL`   | Employee ID is NULL     |

6. What I Learned

Through this assignment, I learned how `GOTO` works in PL/SQL and why structured statements are usually easier to understand. I also learned how to create reusable functions, handle exceptions, use functions inside SQL, and combine different PL/SQL concepts to validate real database information.

7. Conclusion

This assignment gave me practical experience with PL/SQL control structures, functions, and exception handling. It also helped me understand how these concepts can be combined to create simple but useful database solutions.
