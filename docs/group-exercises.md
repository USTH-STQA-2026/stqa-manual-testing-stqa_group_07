# Group Exercises — Discussion & In-depth Study

📖 **Textbook:** Paul Ammann & Jeff Offutt, *Introduction to Software Testing*, 2nd Edition.


*Group:* STQA_Group_07  
*Completion Date:* 29/05/2026

---

## Exercise 1: The "Box" Debate

### 3. Design 6 test values for the "Borrow Book" feature

| # | Source              | Test Value (Description)                        | Specific Data |
|---|---------------------|--------------------------------------------------|---------------|
| 1 | From SRS (Black-box) | Successful borrow (Happy path)                  | Active member + Available book |
| 2 | From SRS (Black-box) | Borrow when reaching 3-book limit               | Member already borrowed 3 books |
| 3 | From SRS (Black-box) | Borrow when member is Suspended                 | Member status = Suspended |
| 4 | From Code (White-box)| Check borrowing limit (currentBorrowCount >= 3) | Member has exactly 3 books |
| 5 | From Code (White-box)| Check book status (book.status != available)   | Book is already Borrowed |
| 6 | From Code (White-box)| Check member status (Expired)                   | Member status = Expired |

### 4. Discussion Questions
a. Test values from SRS and Code overlap on happy path and some negative cases, but code gives more detailed internal conditions (e.g., currentBorrowCount >= maxBooksPerMember).

b. Asking "Is this test Black-box or White-box?" is the *wrong question*.  
We should ask: *"From which level of abstraction was the test designed?"*

---

## Exercise 2: The RIPR Detective

### 1. RIPR Model Diagram
Reachability → Infection → Propagation → Revealability
✅           ✅            ✅             ❌ (Broken!)
text### 2. Discussion Questions
a. The *Revealability* step is broken because the Test Oracle is too weak (only checking "no error" instead of specific expected output).

b. *Improved Expected Result:*
   - Weak: "No error occurs"
   - Strong: "Display message 'No books found' and the book list must be completely empty"

---