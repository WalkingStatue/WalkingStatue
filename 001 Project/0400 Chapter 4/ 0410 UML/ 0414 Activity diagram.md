**Activity Diagram: Managing Personal Finances**
![[Activity Diagram.png]]
**Nodes**:

1. **Start**: The point at which the activity begins.
    
2. **Login**: The user initiates the process by logging in.
    
    - Decision Node: **Successful Login?**
        - Yes: Proceed to "Main Menu"
        - No: Redirect to "Login Failed Message", then loop back to "Login"
3. **Main Menu**: Displayed after a successful login, offering several options.
    
    - **View Transactions**
    - **Set Financial Goals**
    - **Generate Financial Analysis**
    - **Manage Budget**
    - **Logout**
4. **View Transactions**:
    
    - **View All**
    - **View Income**
    - **View Expenses**
    - **Add Transaction**: User inputs details. Once done, goes back to "Main Menu".
    - **Edit Transaction**: User selects a transaction to edit. Once done, goes back to "Main Menu".
    - **Delete Transaction**: User selects a transaction to delete. Once done, goes back to "Main Menu".
5. **Set Financial Goals**:
    
    - **View Existing Goals**
    - **Add New Goal**: User sets a new financial goal. Once done, goes back to "Main Menu".
    - **Edit Goal**: User selects a goal to edit. Once done, goes back to "Main Menu".
    - **Delete Goal**: User selects a goal to delete. Once done, goes back to "Main Menu".
    - **Mark Goal as Achieved**: User marks a goal as achieved. Once done, goes back to "Main Menu".
6. **Generate Financial Analysis**:
    
    - **View Overview**
    - **View Detailed Analysis**
    - **Export Analysis**: Once the report is exported, returns to the "Main Menu".
7. **Manage Budget**:
    
    - **View Current Budget**
    - **Set New Budget**: User inputs budget details. Once done, goes back to "Main Menu".
    - **Edit Budget**: User adjusts the current budget. Once done, goes back to "Main Menu".
    - **Delete Budget**: The user's budget gets deleted. Once done, goes back to "Main Menu".
8. **Logout**: The user logs out and the session ends.
    
9. **End**: The point at which the activity ends.
    

**Flows**:

1. The activity starts at **Start**.
2. The user moves to **Login**.
3. Based on the success of the login, the user may loop through the login process or move to the **Main Menu**.
4. From the **Main Menu**, the user can navigate to various activities: **View Transactions**, **Set Financial Goals**, **Generate Financial Analysis**, or **Manage Budget**. The user can also **Logout**.
5. Within each main activity (like **View Transactions**), there are further sub-activities or tasks. Once completed, the flow typically goes back to the **Main Menu**.
6. The activity ends when the user selects **Logout** and reaches **End**.


**PlantText UML Code**
@startuml
skinparam ActivityBackgroundColor #ffba00
skinparam ActivityBorderColor Black
skinparam ActivityFontColor Black

start
repeat :Login;
backward: Login Failed;
repeat while (Login Successful?) is (No)
-> Yes;

fork

  split

    :View Transaction;
    split
      :Add Transaction;
      split
        :Add Income;
      split again
        :Add Expense;
      end split
    split again
      :Edit Transaction;
      split
        :Edit Income;
      split again
        :Edit Expense;
      end split
    split again
      :Delete Transaction;
      split
        :Delete Income;
      split again
        :Delete Expense;
      end split
    end split

  split again

    :Set Financial Goals;
    split
      :Add New Financial Goal;
    split again
      :Edit Goal;
    split again
      :Delete Goal;
    split again
      :Mark Goal as Achieved;
    end split

  split again

    :Generate Financial Analysis;
    :View Overview;
    :View Detailed Analysis;
    split
      :Export Analysis;
    end split

  split again

    :Manage Budget;
    split
      :Set New Budget;
    split again
      :Edit Budget;
    split again
      :Delete Budget;
    end split

  end split

end fork

:Logout;
stop

@enduml
