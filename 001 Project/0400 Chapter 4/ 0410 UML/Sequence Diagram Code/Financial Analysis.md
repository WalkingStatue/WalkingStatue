![[FinancialAnalysis.png]]
@startuml
skinparam sequence {

ParticipantBorderColor Black
ParticipantBackgroundColor #ffba00

}
participant "User" as U
participant "System" as S
participant "FinancialAnalysis" as FA
participant "Database" as D

U -> S: Access system
activate S
S --> U: Display main menu

group Generate Monthly Summary

  U -> S: Request monthly summary
  S --> U: Choose month to analyze
  U -> S: Confirm month
  activate FA
  S -> FA: generateMonthlySummary()
  FA -> D: Fetch totalIncome & totalExpenses
  D --> FA: Income & expenses data
  FA -> FA: Calculate netSavings & budgetVariance
  FA --> S: Display monthly financial summary
  deactivate FA
  S --> U: Display confirmation

end

group Calculate Net Savings

  U -> S: Request net savings
  S --> U: Choose month to compute
  U -> S: Confirm month
  activate FA
  S -> FA: calculateNetSavings()
  FA -> D: Fetch totalIncome & totalExpenses
  D --> FA: Income & expenses data
  FA --> S: Display net savings for the month
  deactivate FA
  S --> U: Display confirmation

end

group Calculate Budget Variance

  U -> S: Request budget variance
  S --> U: Choose month to compute
  U -> S: Confirm month
  activate FA
  S -> FA: calculateBudgetVariance()
  FA -> D: Fetch set budget & totalExpenses
  D --> FA: Budget & expenses data
  FA --> S: Display budget variance for the month
  deactivate FA
  S --> U: Display confirmation

end
destroy D
destroy U
destroy S
destroy FA
@enduml
