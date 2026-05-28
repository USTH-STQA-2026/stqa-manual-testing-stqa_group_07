# Test Summary Report — ABC Library Borrowing Management System

**Group:** STQA_Group_07  
**Date:** 29/05/2026  
**Tester:** Hà Hiệp Hùng (Group Leader) & Members

---

## 1. Executive Summary

We conducted manual black-box testing on the ABC Library system based on the SRS document. 

- **Total Test Cases Designed & Executed:** 30
- **Passed:** 28 (93.3%)
- **Failed:** 2 (6.7%)
- **Requirements Coverage:** 100% (all 8 REQ)
- **Testing Techniques Used:** Equivalence Partitioning (EP), Boundary Value Analysis (BVA), Decision Table

The system works well for basic functions but has **critical issues** in core business rules (borrowing limit and member status handling).

---

## 2. Test Coverage Summary

| Requirement | Description | Test Cases | Pass/Fail | Coverage |
|-------------|-------------|------------|-----------|----------|
| REQ-01 | Login | TC-01 ~ TC-05 | 5/5 | 100% |
| REQ-02 & REQ-03 | View, Search & Filter Books | TC-06 ~ TC-10 | 5/5 | 100% |
| REQ-04 | Borrow Book | TC-11 ~ TC-15 | 3/5 | 100% |
| REQ-05 | Return Book | TC-19 ~ TC-20 | 2/2 | 100% |
| REQ-07 | Member Management | TC-23 ~ TC-25 | 3/3 | 100% |
| REQ-08 | Borrow Record Lookup | TC-27 ~ TC-28 | 2/2 | 100% |

---

## 3. Defects Summary

| Bug ID | Title | Severity | Related REQ | Status |
|--------|-------|----------|-------------|--------|
| BUG-01 | Member can borrow more than 3 books | High | REQ-04 | Open |
| BUG-02 | Incorrect error message for Suspended member | High | REQ-04 | Open |

**Impact Analysis:**  
These two High-severity bugs violate important business rules, which can lead to incorrect book inventory management and unfair system usage.

---

## 4. Recommendations

**High Priority (Must fix):**
- Fix the borrowing limit enforcement logic (BUG-01)
- Improve member status validation and error messaging (BUG-02)

**Medium Priority:**
- Enhance input validation and user feedback messages
- Consider adding confirmation dialog before borrowing

---

## 5. Conclusion

The ABC Library system has a solid foundation and good UI/UX. However, the critical defects in the borrowing module need to be addressed before deployment. With these fixes, the system would fully meet the SRS requirements.

**Declaration of AI Usage:**  
This project used Grok AI to support structuring test cases, translating to English, and formatting reports. All test execution, bug discovery, and actual results were performed manually by the team.

---

**End of Test Summary Report**