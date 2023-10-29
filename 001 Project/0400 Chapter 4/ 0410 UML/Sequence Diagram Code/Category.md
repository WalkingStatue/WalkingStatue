@startuml
skinparam sequence {

ParticipantBorderColor Black
ParticipantBackgroundColor #ffba00

}
participant "User" as U
participant "System" as S
participant "Category" as C
participant "Database" as D

U -> S: Access system
activate S
S --> U: Display main menu

group Create Category

  U -> S: Add new category
  S --> U: Display category form
  U -> S: Enter category details
  activate C
  S -> C: createCategory()
  C -> D: Store category
  D --> C: Confirmation
  C --> S: Category created confirmation
  deactivate C
  S --> U: Display confirmation

end

group Edit Category

  U -> S: Edit a category
  S --> U: Display category list
  U -> S: Select category to edit
  S --> U: Display edit form with selected category details
  U -> S: Submit updated category details
  activate C
  S -> C: editCategory()
  C -> D: Update category
  D --> C: Update confirmation
  C --> S: Category updated confirmation
  deactivate C
  S --> U: Display confirmation

end

group Delete Category

  U -> S: Delete a category
  S --> U: Display category list
  U -> S: Select category to delete
  activate C
  S -> C: deleteCategory()
  C -> D: Remove category
  D --> C: Deletion confirmation
  C --> S: Category deleted confirmation
  deactivate C
  S --> U: Display confirmation

end
destroy D
destroy U
destroy S
destroy C
@enduml
