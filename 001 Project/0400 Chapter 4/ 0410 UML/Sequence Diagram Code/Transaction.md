![[Transaction.png]]
@startuml
skinparam sequence {

ParticipantBorderColor Black
ParticipantBackgroundColor #ffba00

}
participant "User" as U
participant "System" as S
participant "Transaction" as T
participant "Database" as D

U -> S: Access system
activate S
S --> U: Display main menu

group Add Transaction

  U -> S: Add new transaction
  S --> U: Display transaction type choice (Income/Expense)
  U -> S: Choose type

  alt Income
    S --> U: Display income form
    U -> S: Enter income details & source
    activate T
    S -> T: addIncome()
    T -> D: Store income
    D --> T: Confirmation
    T --> S: Income added confirmation
    deactivate T
    S --> U: Display confirmation
  else Expense
    S --> U: Display expense form
    U -> S: Enter expense details & destination
    activate T
    S -> T: addExpense()
    T -> D: Store expense
    D --> T: Confirmation
    T --> S: Expense added confirmation
    deactivate T
    S --> U: Display confirmation
  end

end

group Edit Transaction

  U -> S: Edit existing transaction
  S --> U: Display transaction list
  U -> S: Select transaction to edit

  alt Income
    S --> U: Display income edit form
    U -> S: Update income details & source
    activate T
    S -> T: editIncome()
    T -> D: Update income
    D --> T: Update confirmation
    T --> S: Income updated confirmation
    deactivate T
    S --> U: Display confirmation
  else Expense
    S --> U: Display expense edit form
    U -> S: Update expense details & destination
    activate T
    S -> T: editExpense()
    T -> D: Update expense
    D --> T: Update confirmation
    T --> S: Expense updated confirmation
    deactivate T
    S --> U: Display confirmation
  end

end

group Delete Transaction

  U -> S: Delete a transaction
  S --> U: Display transaction list
  U -> S: Select transaction to delete

  alt Income
    activate T
    S -> T: deleteIncome()
    T -> D: Remove income
    D --> T: Deletion confirmation
    T --> S: Income deleted confirmation
    deactivate T
    S --> U: Display confirmation
  else Expense
    activate T
    S -> T: deleteExpense()
    T -> D: Remove expense
    D --> T: Deletion confirmation
    T --> S: Expense deleted confirmation
    deactivate T
    S --> U: Display confirmation
  end

end
destroy D
destroy U
destroy S
destroy T
@enduml
