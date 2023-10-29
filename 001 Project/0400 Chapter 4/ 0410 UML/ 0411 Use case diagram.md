
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


**PlantText UML Code**
left to right direction

' Skin parameters to make it more presentable
skinparam usecase {
    BackgroundColor #ffba00
    BorderColor Black
}

' Actors
actor User as "User" #ffba00;line:black;line.bold;

' System boundary
package "Personal Finance Management App" {

    ' Use Cases
    usecase UC1 as "Register/Sign Up"
    usecase UC2 as "Login"
    usecase UC3 as "Logout"
    usecase UC4 as "Add Transaction"
    usecase UC5 as "Edit Transaction"
    usecase UC6 as "Delete Transaction"
    usecase UC7 as "View Transactions"
    usecase UC8 as "Set Monthly Budget"
    usecase UC9 as "View Financial Reports"
    usecase UC10 as "Set Alerts/Notifications"
    usecase UC11 as "Update Profile"
    usecase UC12 as "Reset Password"
    usecase UC13 as "Backup Data"
    usecase UC20 as "Restore Data"
    
    ' Income and Expense Use Cases
    usecase UC14 as "Add Income"
    usecase UC15 as "Add Expense"
    usecase UC16 as "Edit Income"
    usecase UC17 as "Edit Expense"
    usecase UC18 as "Delete Income"
    usecase UC19 as "Delete Expense"
}

' Relationships for User

User --> UC1: registers
User --> UC2: logs in
User --> UC3: logs out
User --> UC4: adds
User --> UC5: edits
User --> UC6: deletes
User --> UC7: views
User --> UC8: sets
User --> UC9: views
User --> UC10: sets
User --> UC11: updates
User --> UC12: resets
User --> UC13: manages
User --> UC20: manages
UC4 ...> UC14: add income
UC4 ...> UC15: add expense
UC5 ...> UC16: edit income
UC5 ...> UC17: edit expense
UC6 ...> UC18: delete income
UC6 ...> UC19: delete expense

@enduml
