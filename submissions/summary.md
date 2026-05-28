# Summary Report — Manual Testing for ABC Library System

**Group:** STQA_Group_07  
**Class:** ICT  
**Semester:** HK2 2025-2026  
**Submission Date:** 28/05/2026  
**Main Tester:** Hà Hiệp Hùng (Team Leader)

---

## 1. Test Execution Overview

| Criteria                        | Quantity   |
|---------------------------------|------------|
| Total Test Cases Executed       | 15         |
| Test Cases Passed               | 13         |
| Test Cases Failed               | 2          |
| Pass Rate                       | **86.7%**  |

**Testing Scope:** REQ-01 to REQ-08 (focused on Borrow/Return functions and Authorization).

---

## 2. Bug Summary

| Bug ID   | Short Description                                   | Severity | Module          |
|----------|-----------------------------------------------------|----------|-----------------|
| BUG-01   | Member can borrow more than the 3-book limit        | High     | Borrow Book     |
| BUG-02   | Wrong error message for Suspended member            | High     | Borrow Book     |

**Comments:**  
Found 2 High severity bugs in the core module (Borrow Book). The system does not properly enforce business rules.

---

## 3. System Quality Evaluation

**Strengths:**
- User-friendly and intuitive interface.
- Search function works well (case-insensitive).
- Basic login and authorization function properly.
- Return book feature works correctly.

**Weaknesses:**
- Borrow Book module does not properly enforce business rules (3-book limit, distinction between Suspended and Expired status).
- Error handling is unclear in some boundary cases.

**Overall Assessment:** The system is at **Average to Good** level. Needs significant improvement in the core borrowing business logic.

---

## 4. Lessons Learned

- Reading the SRS carefully before writing test cases helps define accurate Expected Results.
- Combining multiple test design techniques (EP, BVA, Decision Table) helps discover more defects.
- Always reset data before executing important test cases to ensure independence.
- A good bug report must include clear Steps to Reproduce and supporting screenshots.

---

## 5. Recommendations for Improvement

**For Development Team:**
- Implement validation to limit borrowing to a maximum of 3 books.
- Clearly distinguish error messages between "Suspended" and "Expired" member status.
- Add confirmation dialog before borrowing a book.
- Improve user-friendly error messages.

**For Testing/QA:**
- Create more diverse and comprehensive test data.
- Use Decision Table for all complex business rules.
- Perform Regression Testing after bug fixes.

---

**Conclusion:**  
Through this assignment, the team has gained practical experience in the full manual testing process — from reading SRS to designing test cases, executing tests, reporting bugs, and evaluating software quality. This is a very useful hands-on lesson for the STQA course.

---

