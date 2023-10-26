**Use Case Diagram for Personal Finance Management App:**

**Actors:**

1. **User**: The primary actor who will interact with the system.
2. **System/Admin**: Represents the system or administrators who might manage the backend or resolve user issues.
3. **Banking API** (optional): If the app integrates with banks for real-time transaction data or account balances.

**Use Cases:**

1. **Register/Sign Up**: User creates a new account.
2. **Login**: User logs into the app.
3. **Logout**: User logs out from the app.
4. **Add Transaction**: User adds a new financial transaction (income or expense).
5. **Edit Transaction**: User modifies an existing transaction.
6. **Delete Transaction**: User removes a transaction.
7. **View Transactions**: User views a list or detailed view of transactions.
8. **Set Monthly Budget**: User defines a budget for a particular month or category.
9. **View Financial Reports**: User sees graphical reports, summaries, or insights based on their financial data.
10. **Set Alerts/Notifications**: User sets alerts for specific events, like when nearing budget limits.
11. **Integrate Bank Account**: If the app has this feature, the user can connect their bank account to fetch transaction details automatically.
12. **Update Profile**: User updates personal information or settings.
13. **Reset Password**: User changes or resets the forgotten password.
14. **View Suggestions**: System provides financial insights, tips, or suggestions based on user's spending patterns.
15. **Backup Data**: The system provides an option to backup user data or export transaction details.
16. **Admin Dashboard**: The system or admin monitors user activity, system health, or any other relevant metrics.

**Relationships:**

- **User** interacts with all use cases related to transaction management, budgeting, account settings, and viewing reports.

- **System/Admin** mainly interacts with backend functionalities like admin dashboard or backup data.
 
- If there's a **Banking API**, it would mainly be involved with "Integrate Bank Account" use case