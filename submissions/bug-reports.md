# Bug Reports — ABC Library Borrowing Management System

**Group:** STQA_Group_07  
**Date:** 29/05/2026  
**Based on:** SRS v1.0

---

## BUG-01: Member can borrow more than the 3-book limit

**Severity:** High  
**Priority:** High  
**Related REQ:** REQ-04

**Description:**  
The system fails to enforce the maximum borrowing limit of **3 books** per member.

**Steps to Reproduce:**
1. Login as member (`ba.nguyen@email.com`)
2. Successfully borrow 3 books
3. Attempt to borrow a 4th book

**Expected Result:**  
System should reject the 4th book and show a clear limit warning.

**Actual Result:**  
System allows borrowing the 4th book. Member is currently borrowing **4 books**.

**Evidence:**  
See folder `bug-evidence/bug01.png` 

---

## BUG-02: Incorrect error message for Suspended member

**Severity:** High  
**Priority:** High  
**Related REQ:** REQ-04

**Description:**  
When a **Suspended** member attempts to borrow a book, the system displays the wrong error message ("Member has expired") instead of correctly stating "Suspended".

**Steps to Reproduce:**
1. Reset data
2. Login with suspended account (`cu.le@email.com`)
3. Attempt to borrow an available book

**Expected Result:**  
Show message indicating **Suspended** status.

**Actual Result:**  
Shows incorrect message: "Member has expired. Cannot borrow book."

**Evidence:**  
See folder `bug-evidence/bug02.png` 