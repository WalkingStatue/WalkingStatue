@startuml


skinparam sequence {

ParticipantBorderColor Black
ParticipantBackgroundColor #ffba00

}

participant "User" as U
participant "System" as S
participant "UserClass" as UC
participant "Database" as D



U -> S: Access website
activate S
S --> U: Display homepage

U -> S: Clicks on 'Register' button
S --> U: Display registration form
U -> S: Fills out details & submits
activate UC
S -> UC: register()
UC -> D: Save new user details
D --> UC: Confirmation
UC --> S: Registration successful or error
deactivate UC
S --> U: Display confirmation or error

U -> S: Clicks on 'Login' button
S --> U: Display login form
U -> S: Inputs username & password & submits
activate UC
S -> UC: login()
UC -> D: Verify user credentials
D --> UC: Verification result
UC --> S: Login successful or error
deactivate UC
S --> U: Display user dashboard or error

U -> S: Navigate to 'Profile' settings
S --> U: Display profile details
U -> S: Modifies details & submits changes
activate UC
S -> UC: updateProfile()
UC -> D: Update user details
D --> UC: Update confirmation
UC --> S: Update successful or error
deactivate UC
S --> U: Display confirmation or error

U -> S: Clicks on 'Logout' button
activate UC
S -> UC: logout()
UC --> S: Session terminated
deactivate UC
S --> U: Display homepage or logout confirmation

destroy D
destroy U
destroy S
destroy UC
@enduml
