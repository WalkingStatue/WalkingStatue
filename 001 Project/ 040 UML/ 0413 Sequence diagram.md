**Sequence Diagram: User Operations (Register, Login, Logout, Update Profile)**

**Actors and Objects**:

1. EndUser (The person using the system)
2. UserInterface (UI)
3. UserSystem (This manages the interactions involving the User class)
4. User
5. Database

**Flow**:

**User Registration**

1. **EndUser** -> **UserInterface (UI)**: `clickRegisterOption()`
    
    - Description: The EndUser chooses to register through the interface.
2. **UserInterface (UI)** -> **UserSystem**: `initiateRegistration()`
    
    - Description: The system presents a registration form.
3. **EndUser** -> **UserSystem**: `inputRegistrationDetails(username, email, password)`
    
    - Description: The EndUser fills in registration details.
4. **UserSystem** -> **User**: `register(username, email, password)`
    
    - Description: The `register` method of the User class is invoked.
5. **User** -> **Database**: `storeUserDetails()`
    
    - Description: User details are stored in the database.
6. **Database** -> **UserSystem**: `confirmation()`
    
    - Description: The database sends a confirmation of the successful registration.

**User Login** 7. **EndUser** -> **UserInterface (UI)**: `clickLoginOption()` - Description: The EndUser chooses to log in.

8. **UserInterface (UI)** -> **UserSystem**: `initiateLogin()`
    
    - Description: The system presents a login form.
9. **EndUser** -> **UserSystem**: `inputLoginDetails(username, password)`
    
    - Description: The EndUser fills in login details.
10. **UserSystem** -> **User**: `login(username, password)`
    
    - Description: The `login` method of the User class is invoked.
11. **User** -> **Database**: `checkCredentials()`
    
    - Description: The system checks the provided credentials in the database.
12. **Database** -> **UserSystem**: `loginResult(success/failure)`
    
    - Description: The database sends the result of the login attempt.

**User Logout** 13. **EndUser** -> **UserInterface (UI)**: `clickLogoutOption()` - Description: The EndUser chooses to log out.

14. **UserInterface (UI)** -> **UserSystem**: `initiateLogout()`
    
    - Description: Initiates the logout process.
15. **UserSystem** -> **User**: `logout()`
    
    - Description: The `logout` method of the User class is invoked.

**User Profile Update** 16. **EndUser** -> **UserInterface (UI)**: `clickUpdateProfileOption()` - Description: The EndUser chooses to update their profile.

17. **UserInterface (UI)** -> **UserSystem**: `initiateProfileUpdate()`
    
    - Description: The system presents the user with their current profile details.
18. **EndUser** -> **UserSystem**: `inputUpdatedDetails(newDetails)`
    
    - Description: The EndUser modifies their profile details.
19. **UserSystem** -> **User**: `updateProfile(newDetails)`
    
    - Description: The `updateProfile` method of the User class is invoked.
20. **User** -> **Database**: `storeUpdatedDetails()`
    
    - Description: The updated user details are stored in the database.
21. **Database** -> **UserSystem**: `updateConfirmation()`
    
    - Description: The database sends a confirmation of the successful update.

Transaction
**Sequence Diagram: Transaction Operations (Add, Edit, Delete) with Subclasses**

**Actors and Objects**:

1. EndUser (The person using the system)
2. TransactionInterface (UI specifically designed for transactions)
3. TransactionManager (Manages interactions involving the Transaction class and its methods)
4. Transaction
5. Income (Subclass of Transaction)
6. Expense (Subclass of Transaction)
7. Database

**Flow**:

**Adding an Income Transaction**

1. **EndUser** -> **TransactionInterface**: `clickAddIncomeOption()`
    
    - Description: The EndUser selects the option to add a new income transaction.
2. **TransactionInterface** -> **TransactionManager**: `initiateAddIncome()`
    
    - Description: The system presents a form for adding a new income transaction.
3. **EndUser** -> **TransactionManager**: `inputIncomeDetails(amount, date, source, description)`
    
    - Description: The EndUser provides the necessary income details.
4. **TransactionManager** -> **Income**: `addIncome(amount, date, source, description)`
    
    - Description: The `addIncome` method of the Income subclass is invoked.
5. **Income** -> **Database**: `storeIncomeDetails()`
    
    - Description: Income details are stored in the database.
6. **Database** -> **TransactionManager**: `addConfirmation()`
    
    - Description: The database sends a confirmation of the successful addition.

**Adding an Expense Transaction** 7. **EndUser** -> **TransactionInterface**: `clickAddExpenseOption()` - Description: The EndUser selects the option to add a new expense transaction.

8. **TransactionInterface** -> **TransactionManager**: `initiateAddExpense()`
    
    - Description: The system presents a form for adding a new expense transaction.
9. **EndUser** -> **TransactionManager**: `inputExpenseDetails(amount, date, category, description)`
    
    - Description: The EndUser provides the necessary expense details.
10. **TransactionManager** -> **Expense**: `addExpense(amount, date, category, description)`
    
    - Description: The `addExpense` method of the Expense subclass is invoked.
11. **Expense** -> **Database**: `storeExpenseDetails()`
    
    - Description: Expense details are stored in the database.
12. **Database** -> **TransactionManager**: `addConfirmation()`
    
    - Description: The database sends a confirmation of the successful addition.
   
	**Editing an Income Transaction** 13. **EndUser** -> **TransactionInterface**: `clickEditIncomeOption(transactionID)` - Description: The EndUser selects an income transaction to edit.

14. **TransactionInterface** -> **TransactionManager**: `initiateEditIncome(transactionID)`
    
    - Description: The system presents the current details of the selected income transaction.
15. **EndUser** -> **TransactionManager**: `inputEditedIncomeDetails(newDetails)`
    
    - Description: The EndUser modifies the income details.
16. **TransactionManager** -> **Income**: `editIncome(transactionID, newDetails)`
    
    - Description: The `editIncome` method of the Income subclass is invoked.
17. **Income** -> **Database**: `updateIncomeDetails()`
    
    - Description: The updated income details are stored in the database.
18. **Database** -> **TransactionManager**: `editConfirmation()`
    
    - Description: The database sends a confirmation of the successful edit.

**Editing an Expense Transaction** 19. **EndUser** -> **TransactionInterface**: `clickEditExpenseOption(transactionID)` - Description: The EndUser selects an expense transaction to edit.

20. **TransactionInterface** -> **TransactionManager**: `initiateEditExpense(transactionID)`
    
    - Description: The system presents the current details of the selected expense transaction.
21. **EndUser** -> **TransactionManager**: `inputEditedExpenseDetails(newDetails)`
    
    - Description: The EndUser modifies the expense details.
22. **TransactionManager** -> **Expense**: `editExpense(transactionID, newDetails)`
    
    - Description: The `editExpense` method of the Expense subclass is invoked.
23. **Expense** -> **Database**: `updateExpenseDetails()`
    
    - Description: The updated expense details are stored in the database.
24. **Database** -> **TransactionManager**: `editConfirmation()`
    
    - Description: The database sends a confirmation of the successful edit.

**Deleting an Income Transaction** 25. **EndUser** -> **TransactionInterface**: `clickDeleteIncomeOption(transactionID)` - Description: The EndUser selects an income transaction to delete.

26. **TransactionInterface** -> **TransactionManager**: `confirmIncomeDeletion()`
    
    - Description: The system asks the EndUser for deletion confirmation for the income transaction.
27. **EndUser** -> **TransactionManager**: `confirm()`
    
    - Description: The EndUser confirms the income transaction deletion.
28. **TransactionManager** -> **Income**: `deleteIncome(transactionID)`
    
    - Description: The `deleteIncome` method of the Income subclass is invoked.
29. **Income** -> **Database**: `removeIncome()`
    
    - Description: The specified income transaction is removed from the database.
30. **Database** -> **TransactionManager**: `deleteConfirmation()`
    
    - Description: The database sends a confirmation of the successful deletion.

**Deleting an Expense Transaction** 31. **EndUser** -> **TransactionInterface**: `clickDeleteExpenseOption(transactionID)` - Description: The EndUser selects an expense transaction to delete.

32. **TransactionInterface** -> **TransactionManager**: `confirmExpenseDeletion()`
    
    - Description: The system asks the EndUser for deletion confirmation for the expense transaction.
33. **EndUser** -> **TransactionManager**: `confirm()`
    
    - Description: The EndUser confirms the expense transaction deletion.
34. **TransactionManager** -> **Expense**: `deleteExpense(transactionID)`
    
    - Description: The `deleteExpense` method of the Expense subclass is invoked.
35. **Expense** -> **Database**: `removeExpense()`
    
    - Description: The specified expense transaction is removed from the database.
36. **Database** -> **TransactionManager**: `deleteConfirmation()`
    
    - Description: The database sends a confirmation of the successful deletion.- 