
# Модель прецедентів

**Діаграма прецедентів адміністратора**

</center>
@startuml

    actor "Administrator" as Admin
'----------------------------------------------------------------
    'Проходження опитувань
    usecase completing_surveys as "Брати участь в опитуваннях" <<Completing surveys>> #EA9058
    usecase join_survey as "Долучитися до опитування" <<Join survey>> #FFFFFF
    usecase take_survey as "Пройти опитування" <<Take survey>> #FFFFFF
    usecase see_results as "Подивитись результати" <<See results>> #FFFFFF


    'Керування анкетами опитуваннь
    usecase manage_surveys as "Керування опитуваннями" <<Manage surveys>> #DD8EF6
    usecase create_new_survey as "Створити нове опитування" <<Create new survey>> #FFFFFF
    usecase delete_survey as "Видалити опитування" <<Delete survey>> #FFFFFF
    usecase see_survey_results as "Подивитись результати опитування" <<See survey results>> #FFFFFF
    usecase share_survey_link as "Відправити посиланням на опитування" <<Share survey`s link>> #FFFFFF

    'керування обліковим записом
    usecase account_management as "Керування обліковими записами" <<Account Management>> #C7F151
    usecase registration as "Реєстрація нового облікового запису" <<Registration>> #FFFFFF
    usecase authorization as "Авторізація за наявним обліковим записом" <<Authorization>> #FFFFFF

'----------------------------------------------------------------
    Admin -right-> completing_surveys: extend
    Admin -down-> manage_surveys: extend
    Admin -left-> account_management: extend

    completing_surveys -right-.> join_survey: extend
    completing_surveys -right-.> take_survey: extend
    completing_surveys -down-.> see_results: extend


    manage_surveys -down-.> create_new_survey: extend
    manage_surveys -down-.> delete_survey: extend
    manage_surveys -down-.> share_survey_link: extend
    manage_surveys -down-.> see_survey_results: extend

    account_management -up-.> registration: extend
    account_management -up-.> authorization: extend

@enduml


**Діаграма прецедентів користувача**
</center>
@startuml

    actor "User" as User
'----------------------------------------------------------------
    'Проходження опитувань
    usecase completing_surveys as "Брати участь в опитуваннях" <<Completing surveys>> #EA9058
    usecase join_survey as "Долучитися до опитування" <<Join survey>> #FFFFFF
    usecase take_survey as "Пройти опитування" <<Take survey>> #FFFFFF
    usecase see_results as "Подивитись результати" <<See results>> #FFFFFF


    'керування обліковим записом
    usecase account_management as "Керування обліковими записами" <<Account Management>> #C7F151
    usecase registration as "Реєстрація нового облікового запису" <<Registration>> #FFFFFF
    usecase authorization as "Авторізація за наявним обліковим записом" <<Authorization>> #FFFFFF

'----------------------------------------------------------------
    User -down-> completing_surveys: extend
    User -up-> account_management: extend

    completing_surveys -down-.> join_survey: extend
    completing_surveys -down-.> take_survey: extend
    completing_surveys -down-.> see_results: extend

    account_management -up-.> registration: extend
    account_management -up-.> authorization: extend

@enduml