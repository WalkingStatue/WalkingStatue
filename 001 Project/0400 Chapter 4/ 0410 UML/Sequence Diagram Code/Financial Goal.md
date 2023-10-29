![[FinancialGoal.png]]
@startuml
skinparam sequence {

ParticipantBorderColor Black
ParticipantBackgroundColor #ffba00

}

participant "User" as U
participant "System" as S
participant "FinancialGoal" as FG
participant "Database" as D

U -> S: Access system
activate S
S --> U: Display main menu

group Create Goal

  U -> S: Set new goal
  S --> U: Display goal form
  U -> S: Enter goal details
  activate FG
  S -> FG: createGoal()
  FG -> D: Store goal
  D --> FG: Confirmation
  FG --> S: Goal set confirmation
  deactivate FG
  S --> U: Display confirmation

end

group Update Goal

  U -> S: Modify a goal
  S --> U: Display existing goals
  U -> S: Select & adjust goal details
  activate FG
  S -> FG: updateGoal()
  FG -> D: Update goal
  D --> FG: Update confirmation
  FG --> S: Goal updated confirmation
  deactivate FG
  S --> U: Display confirmation

end

group Delete Goal

  U -> S: Delete a goal
  S --> U: Display existing goals
  U -> S: Select goal to delete
  activate FG
  S -> FG: deleteGoal()
  FG -> D: Remove goal
  D --> FG: Deletion confirmation
  FG --> S: Goal deleted confirmation
  deactivate FG
  S --> U: Display confirmation

end

group Track Goal Progress

  U -> S: Track a goal's progress
  S --> U: Display existing goals
  U -> S: Select goal to track
  activate FG
  S -> FG: trackProgress()
  FG -> D: Fetch currentAmount
  D --> FG: Current amount data
  FG --> S: Display goal progress
  deactivate FG
  S --> U: Display confirmation

end
destroy D
destroy U
destroy S
destroy FG
@enduml
