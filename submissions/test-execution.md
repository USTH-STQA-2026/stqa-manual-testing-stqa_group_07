# Test Execution Result — ABC Library Borrowing Management System

**Group:** STQA_Group_07  
**Executor:** Hà Hiệp Hùng  
**Execution Date:** 28/05/2026

---

## 1. Test Execution Summary

| Criteria                    | Quantity   |
|-----------------------------|------------|
| Total Test Cases Executed   | 15         |
| Test Cases Passed           | 13         |
| Test Cases Failed           | 2          |
| Pass Rate                   | **86.7%**  |

**Testing Scope:** REQ-01 to REQ-08 (focused on Login, Book Search, Borrow/Return, and Authorization).

---

## 2. Detailed Test Execution Results

| TC-ID | Status | Actual Result                                      | Notes                                | Bug ID  |
|-------|--------|----------------------------------------------------|--------------------------------------|---------|
| TC-01 | **Pass** | Login successful, name and role displayed correctly | -                                    | -       |
| TC-03 | **Pass** | Displayed "Member not found"                       | -                                    | -       |
| TC-04 | **Pass** | Displayed "Incorrect password"                     | -                                    | -       |
| TC-05 | **Pass** | Displayed "Please enter email and password"        | -                                    | -       |
| TC-06 | **Pass** | Full book list displayed with correct information  | -                                    | -       |
| TC-07 | **Pass** | Found book when searching "flutter"                | Case-insensitive search works        | -       |
| TC-11 | **Pass** | Book borrowed successfully with success message    | -                                    | -       |
| TC-13 | **Fail** | System allowed borrowing 4th book (limit is 3)    | Does not enforce 3-book limit        | BUG-01  |
| TC-14 | **Fail** | Showed "Member has expired" instead of "Suspended" | Wrong error message for Suspended status | BUG-02  |
| TC-15 | **Pass** | Showed "Member has expired" correctly              | -                                    | -       |
| TC-19 | **Pass** | Book returned successfully with success message    | -                                    | -       |

---

**Notes:**  
- Total of 15 test cases were executed.  
- 2 critical bugs were found in the Borrow Book module.  
- Most core functions (Login, Search, Return) performed as expected.
