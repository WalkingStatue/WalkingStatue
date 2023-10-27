
---

**Use Case Diagram for Personal Finance Management App (3rd Year Final Project):**

**Actors:**

1. **User**: The primary actor who will interact with the system.
2. **System/Admin**: Represents the system or administrators who might manage the backend or resolve user issues.

**Use Cases:**

1. **Register/Sign Up**: User creates a new account.
2. **Login**: User logs into the app.
3. **Logout**: User logs out from the app.
4. **Add Transaction**: User adds a new financial transaction (income or expense).
5. **Edit Transaction**: User modifies an existing transaction.
6. **Delete Transaction**: User removes a transaction.
7. **View Transactions**: User views a list or detailed view of transactions.
8. **Set Monthly Budget**: User defines a budget for a particular month or category.
9. **View Financial Reports**: User sees simple graphical reports or summaries based on their financial data. (Detailed insights might be excluded to simplify the project)
10. **Set Alerts/Notifications**: User sets simple alerts, like when nearing budget limits. (To avoid complexity, real-time notifications might be excluded)
11. **Update Profile**: User updates personal information or settings.
12. **Reset Password**: User changes or resets their password.
13. **Backup Data**: The system provides an option to manually backup user data, perhaps to a simple file format like CSV.

**Relationships:**

- **User** interacts with all use cases related to transaction management, budgeting, account settings, and viewing reports.
- **System/Admin** mainly interacts with backend functionalities like monitoring user activity or backup data.