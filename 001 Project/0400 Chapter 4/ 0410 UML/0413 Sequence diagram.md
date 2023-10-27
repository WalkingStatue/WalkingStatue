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






**Sequence Diagram: Transaction Operations (Add, Edit, Delete) with Subclasses**

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

**Sequence Diagram: Income and Expense Operations

User            System            Income/Expense      Database
 |                |                    |                   |
 |--- Access system ----------------->|                   |
 |<-- Display main menu --------------|                   |

** Add Income **
 |--- Add new income --------------->|                   |
 |<-- Display income form -----------|                   |
 |--- Enter income details & source --|---------------->|
 |                |--- addTransaction() (from Income) --|->  |
 |                |                    |--- Store income ------->|
 |                |                    |<-- Confirmation --------|
 |<-- Income added confirmation -------------------------------|

** Add Expense **
 |--- Add new expense -------------->|                   |
 |<-- Display expense form ---------|                   |
 |--- Enter expense details & destination |------------>|
 |                |--- addTransaction() (from Expense) -|->  |
 |                |                    |--- Store expense ------>|
 |                |                    |<-- Confirmation -------|
 |<-- Expense added confirmation ----------------------------|

** Edit Income **
 |--- Edit existing income --------->|                   |
 |<-- Display income list -----------|                   |
 |--- Select & update income details --|--------------->|
 |                |--- editTransaction() (from Income) -|->  |
 |                |                    |--- Update income ------->|
 |                |                    |<-- Update confirmation -|
 |<-- Income updated confirmation ----------------------------|

** Edit Expense **
 |--- Edit existing expense -------->|                   |
 |<-- Display expense list ---------|                   |
 |--- Select & update expense details |--------------->|
 |                |--- editTransaction() (from Expense) |->  |
 |                |                    |--- Update expense ----->|
 |                |                    |<-- Update confirmation |
 |<-- Expense updated confirmation ---------------------------|

** Delete Income **
 |--- Delete an income ------------->|                   |
 |<-- Display income list ----------|                   |
 |--- Select income to delete ------|----------------->|
 |                |--- deleteTransaction() (from Income) |->  |
 |                |                    |--- Remove income ------->|
 |                |                    |<-- Deletion confirmation|
 |<-- Income deleted confirmation ----------------------------|

** Delete Expense **
 |--- Delete an expense ------------>|                   |
 |<-- Display expense list ---------|                   |
 |--- Select expense to delete -----|----------------->|
 |                |--- deleteTransaction() (from Expense) |-> |
 |                |                    |--- Remove expense ----->|
 |                |                    |<-- Deletion confirmation|
 |<-- Expense deleted confirmation ---------------------------|




**Sequence Diagram: Category Operations (Add, Edit, Delete)**

**Actors and Objects**:

1. EndUser (The person using the system)
2. CategoryInterface (UI designed specifically for categories)
3. CategoryManager (This manages the interactions involving the Category class and its methods)
4. Category
5. Database

**Flow**:

**Adding a Category**

1. **EndUser** -> **CategoryInterface**: `clickAddCategoryOption()`
    - Description: The EndUser selects the option to add a new category.
2. **CategoryInterface** -> **CategoryManager**: `initiateAddCategory()`
    - Description: The system presents a form for adding a new category.
3. **EndUser** -> **CategoryManager**: `inputCategoryDetails(name, description)`
    - Description: The EndUser provides the necessary category details.
4. **CategoryManager** -> **Category**: `addCategory(name, description)`
    - Description: The `addCategory` method of the Category class is invoked.
5. **Category** -> **Database**: `storeCategoryDetails()`
    - Description: Category details are stored in the database.
6. **Database** -> **CategoryManager**: `addConfirmation()`
    - Description: The database sends a confirmation of the successful addition.

**Editing a Category** 
1. **EndUser** -> **CategoryInterface**: `clickEditCategoryOption(categoryID)` 
    - Description: The EndUser selects a category to edit.
2. **CategoryInterface** -> **CategoryManager**: `initiateEditCategory(categoryID)`
    - Description: The system presents the current details of the selected category.
3. **EndUser** -> **CategoryManager**: `inputEditedCategoryDetails(newDetails)`
    - Description: The EndUser modifies the category details.
4. **CategoryManager** -> **Category**: `editCategory(categoryID, newDetails)`
    - Description: The `editCategory` method of the Category class is invoked.
5. **Category** -> **Database**: `updateCategoryDetails()`
    - Description: The updated category details are stored in the database.
6. **Database** -> **CategoryManager**: `editConfirmation()`
    - Description: The database sends a confirmation of the successful edit.

**Deleting a Category** 
1. **EndUser** -> **CategoryInterface**: `clickDeleteCategoryOption(categoryID)` 
    - Description: The EndUser selects a category to delete.
2. **CategoryInterface** -> **CategoryManager**: `confirmDeletion()`
    - Description: The system asks the EndUser for deletion confirmation.
3. **EndUser** -> **CategoryManager**: `confirm()`
    - Description: The EndUser confirms the category deletion.
4. **CategoryManager** -> **Category**: `deleteCategory(categoryID)`
    - Description: The `deleteCategory` method of the Category class is invoked.
5. **Category** -> **Database**: `removeCategory()`
    - Description: The specified category is removed from the database.
6. **Database** -> **CategoryManager**: `deleteConfirmation()`
    - Description: The database sends a confirmation of the successful deletion.


**Sequence Diagram: Budget Operations (Set, Edit, View, Delete)**

**Actors and Objects**:

1. EndUser (The person using the system)
2. BudgetInterface (UI designed specifically for budget operations)
3. BudgetManager (Manages interactions involving the Budget class and its methods)
4. Budget
5. Database

**Flow**:

**Setting a Budget**
1. **EndUser** -> **BudgetInterface**: `clickSetBudgetOption()`
    - Description: The EndUser selects the option to set a new budget.
2. **BudgetInterface** -> **BudgetManager**: `initiateSetBudget()`
    - Description: The system presents a form to set a new budget.
3. **EndUser** -> **BudgetManager**: `inputBudgetDetails(amount, category, duration)`
    - Description: The EndUser provides the necessary details for the new budget.
4. **BudgetManager** -> **Budget**: `setBudget(amount, category, duration)`
    - Description: The `setBudget` method of the Budget class is invoked.
5. **Budget** -> **Database**: `storeBudgetDetails()`
    - Description: Budget details are stored in the database.
6. **Database** -> **BudgetManager**: `setConfirmation()`
    - Description: The database sends a confirmation of the successful budget setup.

**Editing a Budget** 
1. **EndUser** -> **BudgetInterface**: `clickEditBudgetOption(budgetID)`
    - Description: The EndUser selects a specific budget to edit.
2. **BudgetInterface** -> **BudgetManager**: `initiateEditBudget(budgetID)`
    - Description: The system presents the current details of the selected budget.
3. **EndUser** -> **BudgetManager**: `inputEditedBudgetDetails(newDetails)`
    - Description: The EndUser modifies the budget details.
4. **BudgetManager** -> **Budget**: `editBudget(budgetID, newDetails)`
    - Description: The `editBudget` method of the Budget class is invoked.
5. **Budget** -> **Database**: `updateBudgetDetails()`
    - Description: The updated budget details are stored in the database.
6. **Database** -> **BudgetManager**: `editConfirmation()`
    - Description: The database sends a confirmation of the successful edit.

**Viewing a Budget** 
1. **EndUser** -> **BudgetInterface**: `clickViewBudgetOption()` 
    - Description: The EndUser selects the option to view budgets.
2. **BudgetInterface** -> **BudgetManager**: `fetchBudgets()`
    - Description: The interface requests a list of all budgets.
3. **BudgetManager** -> **Database**: `retrieveBudgets()`
    - Description: A request to retrieve all budget data is made to the database.
4. **Database** -> **BudgetManager**: `returnBudgets(budgetsList)`
    - Description: The database returns a list of all budgets.
5. **BudgetManager** -> **BudgetInterface**: `displayBudgets(budgetsList)`
    - Description: The fetched budgets are displayed to the EndUser.


**Deleting a Budget** 
1. **EndUser** -> **BudgetInterface**: `clickDeleteBudgetOption(budgetID)`
    - Description: The EndUser selects a specific budget to delete.
2. **BudgetInterface** -> **BudgetManager**: `confirmDeletion()`
    - Description: The system asks the EndUser for deletion confirmation.
3. **EndUser** -> **BudgetManager**: `confirm()`
    - Description: The EndUser confirms the budget deletion.
4. **BudgetManager** -> **Budget**: `deleteBudget(budgetID)`
    - Description: The `deleteBudget` method of the Budget class is invoked.
5. **Budget** -> **Database**: `removeBudget()`
    - Description: The specified budget is removed from the database.
6. **Database** -> **BudgetManager**: `deleteConfirmation()`
    - Description: The database sends a confirmation of the successful deletion.

**Sequence Diagram: Financial Goal Operations (Set, Edit, View, Achieve, Delete)**

**Actors and Objects**:

1. **EndUser**: The person using the system.
2. **GoalInterface**: UI specifically designed for financial goal operations.
3. **GoalManager**: Manages interactions involving the FinancialGoal class and its methods.
4. **FinancialGoal**
5. **Database**

**Flow**:

**Setting a Financial Goal**

1. **EndUser** -> **GoalInterface**: `clickSetGoalOption()`
    - Description: The EndUser selects the option to set a new financial goal.
2. **GoalInterface** -> **GoalManager**: `initiateSetGoal()`
    - Description: The system presents a form to set a new financial goal.
3. **EndUser** -> **GoalManager**: `inputGoalDetails(title, amount, deadline)`
    - Description: The EndUser provides the necessary details for the new goal.
4. **GoalManager** -> **FinancialGoal**: `setGoal(title, amount, deadline)`
    - Description: The `setGoal` method of the FinancialGoal class is invoked.
5. **FinancialGoal** -> **Database**: `storeGoalDetails()`
    - Description: Goal details are stored in the database.
6. **Database** -> **GoalManager**: `setConfirmation()`
    - Description: The database sends a confirmation of the successful goal setup.

**Editing a Financial Goal** 
1. **EndUser** -> **GoalInterface**: `clickEditGoalOption(goalID)` 
    - Description: The EndUser selects a specific goal to edit.
2. **GoalInterface** -> **GoalManager**: `initiateEditGoal(goalID)`
    - Description: The system presents the current details of the selected goal.
3. **EndUser** -> **GoalManager**: `inputEditedGoalDetails(newDetails)`
    - Description: The EndUser modifies the goal details.
4. **GoalManager** -> **FinancialGoal**: `editGoal(goalID, newDetails)`
    - Description: The `editGoal` method of the FinancialGoal class is invoked.
5. **FinancialGoal** -> **Database**: `updateGoalDetails()`
    - Description: The updated goal details are stored in the database.
6. **Database** -> **GoalManager**: `editConfirmation()`
    - Description: The database sends a confirmation of the successful edit.

**Viewing Financial Goals** 
1. **EndUser** -> **GoalInterface**: `clickViewGoalsOption()` - Description: The EndUser selects the option to view financial goals.
2. **GoalInterface** -> **GoalManager**: `fetchGoals()`
    - Description: The interface requests a list of all goals.
3. **GoalManager** -> **Database**: `retrieveGoals()`
    - Description: A request to retrieve all goal data is made to the database.
4. **Database** -> **GoalManager**: `returnGoals(goalsList)`
    - Description: The database returns a list of all goals.
5. **GoalManager** -> **GoalInterface**: `displayGoals(goalsList)`
    - Description: The fetched goals are displayed to the EndUser.

**Achieving a Financial Goal** 
1. **EndUser** -> **GoalInterface**: `clickAchieveGoalOption(goalID)` 
    - Description: The EndUser indicates they've achieved a specific goal.

2. **GoalInterface** -> **GoalManager**: `markGoalAsAchieved(goalID)`
    - Description: The goal is marked as achieved in the system.
3. **GoalManager** -> **FinancialGoal**: `achieveGoal(goalID)`
    - Description: The `achieveGoal` method of the FinancialGoal class is invoked.
4. **FinancialGoal** -> **Database**: `updateGoalStatus()`
    - Description: The status of the goal is updated in the database to 'achieved'.
5. **Database** -> **GoalManager**: `achieveConfirmation()`
    - Description: The database sends a confirmation of the successful goal achievement.

**Deleting a Financial Goal** 
1. **EndUser** -> **GoalInterface**: `clickDeleteGoalOption(goalID)` 
    - Description: The EndUser selects a specific goal to delete.
2. **GoalInterface** -> **GoalManager**: `confirmDeletion()`
    - Description: The system asks the EndUser for deletion confirmation.
3. **EndUser** -> **GoalManager**: `confirm()`
    - Description: The EndUser confirms the goal deletion.
4. **GoalManager** -> **FinancialGoal**: `deleteGoal(goalID)`
    - Description: The `deleteGoal` method of the FinancialGoal class is invoked.
5. **FinancialGoal** -> **Database**: `removeGoal()`
    - Description: The specified goal is removed from the database.
6. **Database** -> **GoalManager**: `deleteConfirmation()`
    - Description: The database sends a confirmation of the successful deletion.


**Sequence Diagram: Financial Analysis Operations (View Overview, View Detailed Analysis, Export Analysis)**

**Actors and Objects**:

1. **EndUser**: The person using the system.
2. **AnalysisInterface**: UI specifically designed for financial analysis operations.
3. **AnalysisManager**: Manages interactions involving the FinancialAnalysis class and its methods.
4. **FinancialAnalysis**
5. **Database**

**Flow**:

**Viewing Overview of Financial Analysis**

1. **EndUser** -> **AnalysisInterface**: `clickViewAnalysisOverviewOption()`
    - Description: The EndUser selects the option to view an overview of the financial analysis.
2. **AnalysisInterface** -> **AnalysisManager**: `initiateOverview()`
    - Description: The system gets ready to present an overview of the financial analysis.
3. **AnalysisManager** -> **FinancialAnalysis**: `generateOverview()`
    - Description: The `generateOverview` method of the FinancialAnalysis class is invoked.
4. **FinancialAnalysis** -> **Database**: `fetchOverviewData()`
    - Description: Basic financial data for the overview is fetched from the database.
5. **Database** -> **FinancialAnalysis**: `returnOverviewData(overviewData)`
    - Description: The database returns the necessary data.
6. **FinancialAnalysis** -> **AnalysisManager**: `overviewResult(overviewData)`
    - Description: Processed overview data is sent back to the AnalysisManager.
7. **AnalysisManager** -> **AnalysisInterface**: `displayOverview(overviewData)`
    - Description: The analysis overview is displayed to the EndUser.

**Viewing Detailed Financial Analysis** 
1. **EndUser** -> **AnalysisInterface**: `clickViewDetailedAnalysisOption()`
    - Description: The EndUser selects the option to view a detailed financial analysis.
2. **AnalysisInterface** -> **AnalysisManager**: `initiateDetailedAnalysis()`
    - Description: The system prepares to present a detailed financial analysis.
3. **AnalysisManager** -> **FinancialAnalysis**: `generateDetailedAnalysis()`
    - Description: The `generateDetailedAnalysis` method is invoked.
4. **FinancialAnalysis** -> **Database**: `fetchDetailedData()`
    - Description: Detailed financial data is fetched from the database.
5. **Database** -> **FinancialAnalysis**: `returnDetailedData(detailedData)`
    - Description: The database returns the necessary detailed data.
6. **FinancialAnalysis** -> **AnalysisManager**: `detailedAnalysisResult(detailedData)`
    - Description: Processed detailed data is sent back to the AnalysisManager.
7. **AnalysisManager** -> **AnalysisInterface**: `displayDetailedAnalysis(detailedData)`
    - Description: The detailed analysis results are displayed to the EndUser.

**Exporting Financial Analysis** 
1. **EndUser** -> **AnalysisInterface**: `clickExportAnalysisOption()` 
    - Description: The EndUser selects the option to export the financial analysis.
2. **AnalysisInterface** -> **AnalysisManager**: `initiateExport()`
    - Description: The system gets ready to export the financial analysis data.
3. **AnalysisManager** -> **FinancialAnalysis**: `prepareExportData()`
    - Description: The FinancialAnalysis class prepares the data for export.
4. **FinancialAnalysis** -> **Database**: `fetchAllData()`
    - Description: All necessary data for export is fetched from the database.
5. **Database** -> **FinancialAnalysis**: `returnAllData(exportData)`
    - Description: The database returns the data for export.
6. **FinancialAnalysis** -> **AnalysisManager**: `exportResult(exportData)`
    - Description: Processed export data is sent back to the AnalysisManager.
7. **AnalysisManager** -> **AnalysisInterface**: `downloadExportFile(exportFile)`
    - Description: The EndUser is prompted to download the exported analysis file.
