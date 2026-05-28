# Test Cases — ABC Library Borrowing Management System

**Group:** STQA_Group_07  
**Date:** 29/05/2026  
**Based on:** SRS v1.0

---

## TC-01 to TC-05: REQ-01 — Login

| TC-ID | Related REQ | Description | Type | Technique | Precondition | Test Data | Test Steps | Expected Result | Priority |
|-------|-------------|-------------|------|-----------|--------------|-----------|------------|------------------|----------|
| TC-01 | REQ-01 | Successful login as Librarian | Positive | - | Login page | Email: `librarian@library.com`<br>Password: `admin123` | 1. Enter email<br>2. Enter password<br>3. Click Login | Redirect to dashboard, show name + Librarian role | High |
| TC-02 | REQ-01 | Successful login as Member | Positive | - | Login page | Email: `ba.nguyen@email.com`<br>Password: `password123` | 1. Enter email<br>2. Enter password<br>3. Click Login | Redirect to dashboard, show name + Member role | High |
| TC-03 | REQ-01 | Login failed - Wrong email | Negative | EP | Login page | Email: `wrong@email.com`<br>Password: `admin123` | 1. Enter wrong email<br>2. Enter password<br>3. Click Login | Show error: "Không tìm thấy thành viên" | High |
| TC-04 | REQ-01 | Login failed - Wrong password | Negative | EP | Login page | Email: `ba.nguyen@email.com`<br>Password: `wrongpass` | 1. Enter correct email<br>2. Enter wrong password<br>3. Click Login | Show error: "Mật khẩu không đúng" | High |
| TC-05 | REQ-01 | Login failed - Empty fields | Negative | EP | Login page | Email: (empty)<br>Password: (empty) | 1. Leave fields empty<br>2. Click Login | Show error: "Vui lòng nhập email và mật khẩu" | High |

---

## TC-06 to TC-10: REQ-02 & REQ-03 — View, Search & Filter Books

| TC-ID | Related REQ | Description | Type | Technique | Precondition | Test Data | Test Steps | Expected Result | Priority |
|-------|-------------|-------------|------|-----------|--------------|-----------|------------|------------------|----------|
| TC-06 | REQ-02 | View all books after login | Positive | - | Logged in | - | 1. Go to Books tab | Display all books with correct status | High |
| TC-07 | REQ-03 | Search book by name (case-insensitive) | Positive | EP | Logged in | Search: "flutter" | 1. Enter "flutter" in search | Show "Lập trình Flutter cơ bản" | High |
| TC-08 | REQ-03 | Search by author | Positive | EP | Logged in | Search: "Nguyễn Minh Đức" | 1. Enter author name | Show all books by that author | High |
| TC-09 | REQ-03 | Filter by category | Positive | - | Logged in | Filter: "Công nghệ" | 1. Select category "Công nghệ" | Only show books in that category | High |
| TC-10 | REQ-03 | Search with no results | Negative | EP | Logged in | Search: "xyzabc123" | 1. Enter non-existing keyword | Show "Không tìm thấy sách nào" | Medium |

---

## TC-11 to TC-18: REQ-04 — Borrow Book (Decision Table)

| TC-ID | Related REQ | Description | Type | Technique | Precondition | Test Data | Test Steps | Expected Result | Priority |
|-------|-------------|-------------|------|-----------|--------------|-----------|------------|------------------|----------|
| TC-11 | REQ-04 | Borrow book successfully | Positive | - | Logged in as member, book available | Borrow BOOK001 | 1. Click Borrow | Success message + book status changes to "Đang mượn" | High |
| TC-12 | REQ-04 | Cannot borrow when book is already borrowed | Negative | EP | Book is borrowed | Borrow BOOK003 | 1. Try to borrow | Error message | High |
| TC-13 | REQ-04 | Cannot borrow more than 3 books | Negative | BVA | Member has 3 books | Borrow 4th book | 1. Try to borrow 4th book | Reject + show limit message | High |
| TC-14 | REQ-04 | Cannot borrow when member is Suspended | Negative | Decision Table | Login as `cu.le@email.com` | Borrow any available book | 1. Try to borrow | Error: Suspended message | High |
| TC-15 | REQ-04 | Cannot borrow when member is Expired | Negative | Decision Table | Login as `binh.pham@email.com` | Borrow any available book | 1. Try to borrow | Error: Expired message | High |

---

## TC-19 to TC-22: REQ-05 — Return Book

| TC-ID | Related REQ | Description | Type | Technique | Precondition | Test Data | Test Steps | Expected Result | Priority |
|-------|-------------|-------------|------|-----------|--------------|-----------|------------|------------------|----------|
| TC-19 | REQ-05 | Return book successfully | Positive | - | Has borrowed book | Return a book | 1. Go to Borrow/Return tab<br>2. Click Return | Success message + book status = "Có sẵn" | High |
| TC-20 | REQ-05 | Return overdue book with warning | Positive | - | Overdue book | Return overdue book | 1. Return book | Success + overdue warning | High |

---

## TC-23 to TC-26: REQ-07 — Member Management

| TC-ID | Related REQ | Description | Type | Technique | Precondition | Test Data | Test Steps | Expected Result | Priority |
|-------|-------------|-------------|------|-----------|--------------|-----------|------------|------------------|----------|
| TC-23 | REQ-07 | Add new member successfully (Librarian) | Positive | - | Login as Librarian | Valid email | 1. Go to Members tab<br>2. Add new member | Member created successfully | High |
| TC-24 | REQ-07 | Invalid email (no dot) | Negative | EP | Login as Librarian | Email: `test@domain` | 1. Enter invalid email | Error message | High |
| TC-25 | REQ-07 | Duplicate email | Negative | EP | Login as Librarian | Existing email | 1. Enter duplicate email | Error: Email already exists | High |

---

## TC-27 to TC-30: REQ-08 — Borrow Record Lookup

| TC-ID | Related REQ | Description | Type | Technique | Precondition | Test Data | Test Steps | Expected Result | Priority |
|-------|-------------|-------------|------|-----------|--------------|-----------|------------|------------------|----------|
| TC-27 | REQ-08 | Member cannot view others' records | Negative | - | Login as Member | - | 1. Try to view other member's record | Access denied | High |
| TC-28 | REQ-08 | Librarian can view all records | Positive | - | Login as Librarian | - | 1. Search by member ID | Can view all borrow records | High |

---

**Total Test Cases: 30**  
**Techniques Used:** Equivalence Partitioning (EP), Boundary Value Analysis (BVA), Decision Table

---

