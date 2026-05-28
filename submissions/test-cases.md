# Test Cases — ABC Library Borrowing Management System

**Group:** STQA_Group_07  
**Date Created:** 28/05/2026  
**Based on:** SRS v1.0

---

## TC-01 to TC-05: REQ-01 — Login

| TC-ID | Description | Type | Technique | Precondition | Test Data | Test Steps | Expected Result | Priority |
|-------|-------------|------|-----------|--------------|-----------|------------|------------------|----------|
| **TC-01** | Successful login with Librarian account | Positive | - | Login page | Email: `librarian@library.com`<br>Password: `admin123` | 1. Enter email<br>2. Enter password<br>3. Click Login | Redirect to homepage. Display name and Librarian role on AppBar | High |
| **TC-02** | Successful login with Member account | Positive | - | Login page | Email: `ba.nguyen@email.com`<br>Password: `password123` | 1. Enter email<br>2. Enter password<br>3. Click Login | Redirect to homepage. Display name and Member role on AppBar | High |
| **TC-03** | Login failed - Invalid email | Negative | EP | Login page | Email: `nobody@test.com`<br>Password: `admin123` | 1. Enter wrong email<br>2. Enter password<br>3. Click Login | Display: "Member not found" | High |
| **TC-04** | Login failed - Wrong password | Negative | EP | Login page | Email: `ba.nguyen@email.com`<br>Password: `wrongpassword` | 1. Enter correct email<br>2. Enter wrong password<br>3. Click Login | Display: "Incorrect password" | High |
| **TC-05** | Login failed - Empty fields | Negative | EP | Login page | Email & Password empty | 1. Leave both fields empty<br>2. Click Login | Display: "Please enter email and password" | Medium |

---

## TC-06 to TC-10: REQ-02 & REQ-03 — View & Search Books

| TC-ID | Description | Type | Technique | Precondition | Test Data | Test Steps | Expected Result | Priority |
|-------|-------------|------|-----------|--------------|-----------|------------|------------------|----------|
| **TC-06** | View book list | Positive | - | Logged in | - | 1. Go to **Books** tab | Display full list of books with complete information | High |
| **TC-07** | Search books (case-insensitive) | Positive | EP | Logged in as Member | Keyword: `flutter` | 1. Enter "flutter" | Display book "Lập trình Flutter cơ bản" | High |
| **TC-08** | Search by author | Positive | EP | Logged in as Member | Keyword: `Nguyễn Minh Đức` | 1. Enter author name | Display books by that author | High |
| **TC-09** | Filter by category | Positive | EP | Logged in as Member | Category: Công nghệ | 1. Filter by "Công nghệ" | Only books in Công nghệ category are shown | Medium |
| **TC-10** | Search with no results | Negative | EP | Logged in as Member | Keyword: `xyzabc123` | 1. Enter non-existent keyword | Display: "No books found" | Medium |

---

## TC-11 to TC-18: REQ-04 — Borrow Book (Critical Module)

| TC-ID | Description | Type | Technique | Precondition | Test Data | Test Steps | Expected Result | Priority |
|-------|-------------|------|-----------|--------------|-----------|------------|------------------|----------|
| **TC-11** | Successful book borrowing | Positive | - | Logged in as Member + Reset data | Book BOOK001 (Available) | 1. Select book<br>2. Click Borrow | Book status changes to "Borrowed", borrow record created with 14-day due date | High |
| **TC-12** | Borrow already borrowed book | Negative | EP | Logged in as Member | Book BOOK003 (Borrowed) | 1. Select borrowed book<br>2. Click Borrow | Borrow is rejected | High |
| **TC-13** | Borrow when limit of 3 books is reached | Negative | BVA | Member has borrowed 3 books | - | 1. Try to borrow 4th book | Borrow rejected + limit message shown | High |
| **TC-14** | Borrow when member is Suspended | Negative | Decision Table | Login as MEM004 (Suspended) | Available book | 1. Suspended member tries to borrow | Rejected with correct reason **Suspended** | High |
| **TC-15** | Borrow when member is Expired | Negative | Decision Table | Login as MEM005 (Expired) | Available book | 1. Expired member tries to borrow | Rejected with correct reason **Expired** | High |
| **TC-16** | Verify borrowing period is 14 days | Positive | BVA | Logged in as Member | - | 1. Borrow book successfully | Due date = Borrow date + 14 days | High |
| **TC-17** | Borrow lost book | Negative | EP | Logged in as Member | Book BOOK007 (Lost) | 1. Try to borrow lost book | Cannot borrow | Medium |
| **TC-18** | Borrow at exact boundary (3 books) | Negative | BVA | Member has exactly 3 books | - | 1. Try to borrow 4th book | Rejected | High |

---

## TC-19 to TC-22: REQ-05 & REQ-06 — Return Book & Overdue Handling

| TC-ID | Description | Type | Technique | Precondition | Test Data | Test Steps | Expected Result | Priority |
|-------|-------------|------|-----------|--------------|-----------|------------|------------------|----------|
| **TC-19** | Successful book return | Positive | - | Member has borrowed book | - | 1. Go to Borrow/Return tab<br>2. Select borrowed book<br>3. Click Return | Book status changes to "Available" | High |
| **TC-20** | Display overdue warning | Positive | - | There is overdue record | - | 1. Librarian clicks "Check Overdue" | Overdue warning is displayed | High |
| **TC-21** | Member can only view their own borrow records | Positive | - | Logged in as Member | - | 1. Go to Borrow/Return tab | Only own borrow records are shown | High |
| **TC-22** | Librarian can view all borrow records | Positive | - | Logged in as Librarian | - | 1. Search borrow records | Can view all members' records | High |

---

## TC-23 to TC-26: REQ-07 — Member Management

| TC-ID | Description | Type | Technique | Precondition | Test Data | Test Steps | Expected Result | Priority |
|-------|-------------|------|-----------|--------------|-----------|------------|------------------|----------|
| **TC-23** | Add new member successfully | Positive | - | Logged in as Librarian | Valid email | 1. Go to Members tab and add new member | Member created successfully | High |
| **TC-24** | Add member with invalid email (missing dot) | Negative | EP | Logged in as Librarian | Email: `test@domain` | 1. Enter invalid email | Rejected + invalid email error | High |
| **TC-25** | Add member with duplicate email | Negative | EP | Logged in as Librarian | Existing email | 1. Enter existing email | Rejected + duplicate email message | High |
| **TC-26** | Member cannot access Members tab | Negative | - | Logged in as Member | - | 1. Try to access Members tab | Tab is hidden or access denied | High |

---

## TC-27 to TC-28: REQ-08 — Borrow Record Lookup

| TC-ID | Description | Type | Technique | Precondition | Test Data | Test Steps | Expected Result | Priority |
|-------|-------------|------|-----------|--------------|-----------|------------|------------------|----------|
| **TC-27** | Member cannot view other members' records | Negative | - | Logged in as Member | - | 1. Try to view other member's record | Access denied | High |
| **TC-28** | Librarian can view all borrow records | Positive | - | Logged in as Librarian | - | 1. Search by member ID | Can view all borrow records | High |

---

**Total:** 32 Test Cases

**Test Design Techniques Used:** Equivalence Partitioning (EP), Boundary Value Analysis (BVA), Decision Table