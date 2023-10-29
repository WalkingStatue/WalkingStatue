[[0000 Index]]

### User Class:

| Field Name   | Type   | Size | Description                                                   | Constraints    |
|--------------|--------|------|---------------------------------------------------------------|----------------|
| userID       | Int    | -    | Unique identifier for each user.                              | Primary Key    |
| username     | String | 50   | User's chosen name for the platform.                          | Not Null       |
| password     | String | 256  | Encrypted password for user authentication.                   | Not Null       |
| email        | String | 100  | User's email address for communication/password recovery.     | Not Null       |
| dateJoined   | Date   | -    | Date when the user registered on the platform.                | Not Null       |

### Transaction Class:

| Field Name      | Type      | Size | Description                                                   | Constraints                              |
|-----------------|-----------|------|---------------------------------------------------------------|------------------------------------------|
| transactionID   | Int       | -    | Unique identifier for each transaction.                       | Primary Key                              |
| amount          | Float     | -    | Monetary value of the transaction.                            | Not Null                                 |
| date            | Date      | -    | Date the transaction occurred.                                | Not Null                                 |
| description     | String    | 500  | Details about the transaction.                                | Not Null                                 |
| category        | Category  | -    | Type or classification of the transaction.                    | Foreign Key (categoryID from Category)   |

### Income Class (Subclass of Transaction):

| Field Name      | Type      | Size | Description                                                   | Constraints    |
|-----------------|-----------|------|---------------------------------------------------------------|----------------|
| source          | String    | 100  | Describes the origin of the income (e.g., Salary, Gift).      | Not Null       |

### Expense Class (Subclass of Transaction):

| Field Name      | Type      | Size | Description                                                   | Constraints    |
|-----------------|-----------|------|---------------------------------------------------------------|----------------|
| destination     | String    | 100  | Describes where the money was spent (e.g., Groceries, Rent).  | Not Null       |

### Category Class:

| Field Name      | Type      | Size | Description                                                   | Constraints    |
|-----------------|-----------|------|---------------------------------------------------------------|----------------|
| categoryID      | Int       | -    | Unique identifier for each category.                          | Primary Key    |
| name            | String    | 100  | Name of the category (e.g., Travel, Food).                    | Not Null       |
| type            | String    | 50   | Indicates if it's an income or expense category.              | Not Null       |

### Budget Class:

| Field Name      | Type      | Size | Description                                                   | Constraints                              |
|-----------------|-----------|------|---------------------------------------------------------------|------------------------------------------|
| budgetID        | Int       | -    | Unique identifier for each budget entry.                      | Primary Key                              |
| month           | Date      | -    | Month the budget is set for.                                  | Not Null                                 |
| amount          | Float     | -    | Monetary limit set for the budget.                            | Not Null                                 |
| category        | Category  | -    | Specific type or classification of the budget.                | Foreign Key (categoryID from Category)   |

### FinancialGoal Class:

| Field Name      | Type      | Size | Description                                                   | Constraints    |
|-----------------|-----------|------|---------------------------------------------------------------|----------------|
| goalID          | Int       | -    | Unique identifier for each financial goal.                    | Primary Key    |
| name            | String    | 100  | Title or name of the financial goal.                          | Not Null       |
| targetAmount    | Float     | -    | Desired monetary value to achieve.                            | Not Null       |
| targetDate      | Date      | -    | Date by which user aims to achieve the goal.                  | Not Null       |
| currentAmount   | Float     | -    | Current monetary value saved or accumulated towards the goal. | Not Null       |
| description     | String    | 500  | Further details about the goal.                               | Optional       |

### FinancialAnalysis Class:

| Field Name      | Type      | Size | Description                                                   | Constraints                            |
|-----------------|-----------|------|---------------------------------------------------------------|----------------------------------------|
| analysisID      | Int       | -    | Unique identifier for each financial analysis entry.          | Primary Key                            |
| userID          | Int       | -    | Identifier linking the analysis to a specific user.           | Foreign Key (userID from User)         |
| month           | Date      | -    | The specific month being analyzed.                            | Not Null                               |
| totalIncome     | Float     | -    | Sum of all income for the month.                              | Not Null                               |
| totalExpenses   | Float     | -    | Sum of all expenses for the month.                            | Not Null                               |
| netSavings      | Float     | -    | Difference between total income and total expenses.           | Computed                               |
| budgetVariance  | Float     | -    | Difference between the set budget and actual expenses.        | Computed                               |
