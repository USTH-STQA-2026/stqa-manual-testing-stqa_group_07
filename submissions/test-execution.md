# Test Execution Result — ABC Library Borrowing Management System

**Group:** STQA_Group_07  
**Executor:** Hà Hiệp Hùng  
**Execution Date:** 29/05/2026  
**Based on:** SRS v1.0

---

## 1. Test Execution Summary

| Criteria                    | Quantity    |
|-----------------------------|-------------|
| Total Test Cases Executed   | **30**      |
| Test Cases Passed           | **28**      |
| Test Cases Failed           | **2**       |
| Pass Rate                   | **93.3%**   |

**Testing Scope:** All 8 functional requirements (REQ-01 to REQ-08)

---

## 2. Detailed Test Execution Results

| TC-ID | Status | Actual Result | Notes | Bug ID |
|-------|--------|---------------|-------|--------|
| TC-01 | Pass   | Login successful, name and role displayed | - | - |
| TC-02 | Pass   | Login successful, name and role displayed | - | - |
| TC-03 | Pass   | Showed "Không tìm thấy thành viên" | - | - |
| TC-04 | Pass   | Showed "Mật khẩu không đúng" | - | - |
| TC-05 | Pass   | Showed "Vui lòng nhập email và mật khẩu" | - | - |
| TC-06 | Pass   | All books displayed correctly | - | - |
| TC-07 | Pass   | Found book with "flutter" search | Case-insensitive works | - |
| TC-08 | Pass   | Author search worked correctly | - | - |
| TC-09 | Pass   | Category filter worked correctly | - | - |
| TC-10 | Pass   | Showed "Không tìm thấy sách nào" | - | - |
| TC-11 | Pass   | Borrowed book successfully | - | - |
| TC-12 | Pass   | Cannot borrow already borrowed book | - | - |
| TC-13 | **Fail** | Allowed borrowing 4th book (limit is 3) | Violates REQ-04 | BUG-01 |
| TC-14 | **Fail** | Showed "Member has expired" for Suspended member | Wrong error message | BUG-02 |
| TC-15 | Pass   | Showed correct error for Expired member | - | - |
| TC-19 | Pass   | Book returned successfully | - | - |
| TC-20 | Pass   | Overdue warning displayed correctly | - | - |
| TC-23 | Pass   | Added new member successfully | - | - |
| TC-24 | Pass   | Invalid email rejected | - | - |
| TC-25 | Pass   | Duplicate email rejected | - | - |
| TC-27 | Pass   | Member cannot view others' records | - | - |
| TC-28 | Pass   | Librarian can view all records | - | - |

**Note:** Remaining test cases (TC-16, TC-17, TC-18, TC-21, TC-22, TC-26, TC-29, TC-30) were executed and all **Passed**.

---

## 3. Overall Comments
- Most functions work as expected according to SRS.
- 2 critical bugs were discovered in the Borrow Book module (REQ-04).
- Pass rate is high, but business rule enforcement needs improvement.
