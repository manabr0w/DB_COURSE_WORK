# Проєктування бази даних
 
 
## Модель бізнес-об'єктів

@startuml

entity Permission #14f749
entity Permission.id
entity Permission.name
entity Permission.description
entity Permission.role_permission

Permission.id --* Permission
Permission.name --* Permission
Permission.description --* Permission
Permission.role_permission --* Permission 
 
entity Role #0c56bd
entity Role.id
entity Role.user_role
entity Role.description
entity Role.name

Role.id --* Role
Role.user_role --* Role
Role.description --* Role
Role.name --* Role
Permission.role_permission -u- Role

entity User #bd0c65
entity User.id
entity User.name
entity User.lastname
entity User.password

User.id --* User
User.name --* User
User.lastname --* User
User.password --* User
Role.user_role -u- User

entity Survey #e9d201
entity Survey.id
entity Servey.user_id
entity Survey.name
entity Survey.description
entity Servey.result

Survey.id --* Survey
Servey.user_id --* Survey
Survey.name --* Survey
Survey.description --* Survey
Servey.result --* Survey
User -r- Servey.user_id

entity Result #00ff61
entity Result.id
entity Result.description
entity Result.name

Result.id --* Result
Result.description --* Result
Result.name --* Result
Servey.result -u- Result

@enduml 

- ER-модель
##  Реляційна схема

![relational-schema](https://github.com/user-attachments/assets/cf55f090-77ab-4c5a-89e2-a522d5a49361)



