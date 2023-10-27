**Sequence Diagram: User Registration and Authentication**

User           System         UserClass       Database
 |               |               |               |
 |--- Access website ---------->|               |
 |<-- Display homepage ---------|               |
 |--- Click 'Register' -------->|               |
 |<-- Display registration -----|               |
 |--- Fill out details & submit-|-------------->|
 |               |--- register()-|->            |
 |               |               |--- Save details ------->|
 |               |               |<-- Confirmation -------|
 |<-- Registration success or error ---------------------|
 |--- Click 'Login' ----------->|               |
 |<-- Display login form ------|               |
 |--- Inputs username & password|-------------->|
 |               |--- login()---|->            |
 |               |               |--- Verify credentials -->|
 |               |               |<-- Verification --------|
 |<-- Login success or error -----------------------------|
 |--- Navigate to 'Profile' --->|               |
 |<-- Display profile details -|               |
 |--- Modifies details & submit-|-------------->|
 |               |--- updateProfile()---|->    |
 |               |               |--- Update details ------->|
 |               |               |<-- Update confirmation --|
 |<-- Update success or error -----------------------------|
 |--- Click 'Logout' ---------->|               |
 |               |--- logout() -|->            |
 |<-- Session terminated -------|               |
 |<-- Display homepage ---------|               |


**Sequence Diagram: Transaction Operations**

User            System            Transaction      Database
 |                |                  |                 |
 |--- Access system --------------->|                 |
 |<-- Display main menu ------------|                 |
 |--- Add new transaction -------->|                 |
 |<-- Display transaction form ----|                 |
 |--- Enter transaction details ----|-------------->|
 |                |--- addTransaction()---|->      |
 |                |                  |--- Store transaction ------->|
 |                |                  |<-- Confirmation ------------|
 |<-- Transaction added confirmation-----------------------------|
 |--- Edit existing transaction --->|                 |
 |<-- Display transaction list ----|                 |
 |--- Select & update details ------|-------------->|
 |                |--- editTransaction()---|->     |
 |                |                  |--- Update transaction ------>|
 |                |                  |<-- Update confirmation -----|
 |<-- Transaction updated confirmation--------------------------|
 |--- Delete a transaction -------->|                 |
 |<-- Display transaction list ----|                 |
 |--- Select transaction to delete --|-------------->|
 |                |--- deleteTransaction()--|->    |
 |                |                  |--- Remove transaction ------>|
 |                |                  |<-- Deletion confirmation --|
 |<-- Transaction deleted confirmation--------------------------|

**Sequence Diagram: Income and Expense Operations**

User            System            Income/Expense      Database
 |                |                    |                   |
 |--- Access system ----------------->|                   |
 |<-- Display main menu --------------|                   |

**Add Income**
 |--- Add new income --------------->|                   |
 |<-- Display income form -----------|                   |
 |--- Enter income details & source --|---------------->|
 |                |--- addTransaction() (from Income) --|->  |
 |                |                    |--- Store income ------->|
 |                |                    |<-- Confirmation --------|
 |<-- Income added confirmation -------------------------------|

**Add Expense**
 |--- Add new expense -------------->|                   |
 |<-- Display expense form ---------|                   |
 |--- Enter expense details & destination |------------>|
 |                |--- addTransaction() (from Expense) -|->  |
 |                |                    |--- Store expense ------>|
 |                |                    |<-- Confirmation -------|
 |<-- Expense added confirmation ----------------------------|

**Edit Income**
 |--- Edit existing income --------->|                   |
 |<-- Display income list -----------|                   |
 |--- Select & update income details --|--------------->|
 |                |--- editTransaction() (from Income) -|->  |
 |                |                    |--- Update income ------->|
 |                |                    |<-- Update confirmation -|
 |<-- Income updated confirmation ----------------------------|

**Edit Expense**
 |--- Edit existing expense -------->|                   |
 |<-- Display expense list ---------|                   |
 |--- Select & update expense details |--------------->|
 |                |--- editTransaction() (from Expense) |->  |
 |                |                    |--- Update expense ----->|
 |                |                    |<-- Update confirmation |
 |<-- Expense updated confirmation ---------------------------|

**Delete Income**
 |--- Delete an income ------------->|                   |
 |<-- Display income list ----------|                   |
 |--- Select income to delete ------|----------------->|
 |                |--- deleteTransaction() (from Income) |->  |
 |                |                    |--- Remove income ------->|
 |                |                    |<-- Deletion confirmation|
 |<-- Income deleted confirmation ----------------------------|

**Delete Expense**
 |--- Delete an expense ------------>|                   |
 |<-- Display expense list ---------|                   |
 |--- Select expense to delete -----|----------------->|
 |                |--- deleteTransaction() (from Expense) |-> |
 |                |                    |--- Remove expense ----->|
 |                |                    |<-- Deletion confirmation|
 |<-- Expense deleted confirmation ---------------------------|


**Sequence Diagram: Category Operations**

User             System          Category       Database
 |                 |                |               |
 |--- Access system -------------->|               |
 |<-- Display main menu -----------|               |

**Create Category**
 |--- Add new category ----------->|               |
 |<-- Display category form -------|               |
 |--- Enter category details ------|------------->|
 |                 |--- createCategory() ---|->   |
 |                 |                |--- Store category ------->|
 |                 |                |<-- Confirmation ----------|
 |<-- Category created confirmation --------------------------|

**Delete Category**
 |--- Delete a category ---------->|               |
 |<-- Display category list -------|               |
 |--- Select category to delete ---|------------->|
 |                 |--- deleteCategory() ---|->   |
 |                 |                |--- Remove category ------->|
 |                 |                |<-- Deletion confirmation --|
 |<-- Category deleted confirmation ---------------------------|


**Sequence Diagram: Budget Operations**
**Sequence Diagram: Financial Goal Operations**
**Sequence Diagram: Financial Analysis Operations**

