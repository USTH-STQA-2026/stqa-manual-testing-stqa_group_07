# Bug Reports — ABC Library Borrowing Management System

**Group:** STQA_Group_07  
**Date:** 28/05/2026

---

## BUG-01: Member can borrow more than the 3-book limit

**Severity:** High  
**Priority:** High  
**Date Found:** 28/05/2026

### Description
The system allows members to borrow more than the maximum limit of **3 books** at the same time, violating the requirement in REQ-04.

### Steps to Reproduce
1. Login with a member account (`ba.nguyen@email.com`)
2. Successfully borrow 3 books
3. Try to borrow a 4th book
4. The system allows the borrow to succeed

### Expected Result
The system should reject the 4th book and display a message that the borrowing limit has been reached.

### Actual Result
The system allows the 4th book to be borrowed successfully. The member is currently borrowing **4 books**.


**Screenshot:**
![BUG-01](../screenshots/bug01_mượn_4_sach.png)

---

## BUG-02: System shows incorrect error message for Suspended member

**Severity:** High  
**Priority:** High  
**Date Found:** 28/05/2026

### Description
When a **Suspended** member tries to borrow a book, the system incorrectly displays the message **"Member has expired"** instead of the correct reason "Suspended". The system fails to distinguish between "Suspended" and "Expired" status.

### Steps to Reproduce
1. Reset data to initial state
2. Login with suspended account (`cu.le@email.com`)
3. Try to borrow an available book
4. The system shows incorrect error message

### Expected Result
The system should reject the borrow and display a message related to **"Suspended"** status.

### Actual Result
The system displays incorrect message: **"Member has expired. Cannot borrow book."**


**Screenshot:**
![BUG-02](../screenshots/bug02_sai_thong_bao_tam_ngung.png)