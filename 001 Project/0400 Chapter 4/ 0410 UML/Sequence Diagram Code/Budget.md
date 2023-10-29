![[Budget.png]]
@startuml
skinparam sequence {

ParticipantBorderColor Black
ParticipantBackgroundColor #ffba00

}
participant "User" as U
participant "System" as S
participant "Budget" as B
participant "Database" as D

U -> S: Access system
activate S
S --> U: Display main menu

group Set Budget

  U -> S: Set new budget
  S --> U: Display budget form
  U -> S: Enter budget details & category
  activate B
  S -> B: setBudget()
  B -> D: Store budget
  D --> B: Confirmation
  B --> S: Budget set confirmation
  deactivate B
  S --> U: Display confirmation

end

group Adjust Budget

  U -> S: Modify a budget
  S --> U: Display existing budgets
  U -> S: Select & adjust details
  activate B
  S -> B: adjustBudget()
  B -> D: Update budget
  D --> B: Update confirmation
  B --> S: Budget adjusted confirmation
  deactivate B
  S --> U: Display confirmation

end

group Delete Budget

  U -> S: Delete a budget
  S --> U: Display existing budgets
  U -> S: Select budget to delete
  activate B
  S -> B: deleteBudget()
  B -> D: Remove budget
  D --> B: Deletion confirmation
  B --> S: Budget deleted confirmation
  deactivate B
  S --> U: Display confirmation

end
destroy D
destroy U
destroy S
destroy B
@enduml
