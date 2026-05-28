# Bug Reports — ABC Library Borrowing Management System

**Group:** STQA_Group_07  
**Date:** 28/05/2026

---

## BUG-01: Member can borrow more than the 3-book limit

**Severity:** High  
**Priority:** High  
**Date Found:** 28/05/2026

**Description:**  
The system allows members to borrow more than the maximum limit of **3 books** at the same time.

**Steps to Reproduce:**  
1. Login with member account (`ba.nguyen@email.com`)  
2. Successfully borrow 3 books  
3. Try to borrow a 4th book  

**Expected Result:** System should reject and show limit message.  
**Actual Result:** System allows borrowing the 4th book.

**Evidence:** See `bug-evidence/bug01_muon_qua_gioi_han.png`

---

## BUG-02: System shows incorrect error message for Suspended member

**Severity:** High  
**Priority:** High  
**Date Found:** 28/05/2026

**Description:**  
When a Suspended member tries to borrow a book, the system shows "Member has expired" instead of "Suspended".

**Steps to Reproduce:**  
1. Reset data  
2. Login with `cu.le@email.com` (Suspended)  
3. Try to borrow an available book  

**Expected Result:** Show message related to "Suspended".  
**Actual Result:** Shows "Member has expired...".

**Evidence:** See `bug-evidence/bug02_sai_thong_bao.png`