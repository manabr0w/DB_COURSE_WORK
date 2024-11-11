
# Модель прецедентів

В цьому файлі необхідно перелічити всі документи, розроблені в проекті та дати посилання на них.

*Модель прецедентів повинна містити загальні оглядові діаграми та специфікації прецедентів.*



Вбудовування зображень діаграм здійснюється з використанням сервісу [plantuml.com](https://plantuml.com/). 

В markdown-файлі використовується опис діаграми

```md

<center style="
    border-radius:4px;
    border: 1px solid #cfd7e6;
    box-shadow: 0 1px 3px 0 rgba(89,105,129,.05), 0 1px 1px 0 rgba(0,0,0,.025);
    padding: 1em;"
>

@startuml

    actor "Administrator" as Admin
'----------------------------------------------------------------
    'Проходження опитувань
    usecase completing_surveys as "Брати участь в опитуваннях" <<Completing surveys>> #EA9058
    usecase join_survey as "Долучитися до опитування" <<Join survey>> #FFFFFF
    usecase take_survey as "Пройти опитування" <<Take survey>> #FFFFFF

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
    Admin -up-> account_management: extend

    completing_surveys -right-.> join_survey: extend
    completing_surveys -right-.> take_survey: extend

    manage_surveys -down-.> create_new_survey: extend
    manage_surveys -down-.> delete_survey: extend
    manage_surveys -down-.> share_survey_link: extend
    manage_surveys -down-.> see_survey_results: extend

    account_management -up-.> registration: extend
    account_management -up-.> authorization: extend

@enduml

**Діаграма прецедентів**

</center>
```

яка буде відображена наступним чином

<center style="
    border-radius:4px;
    border: 1px solid #cfd7e6;
    box-shadow: 0 1px 3px 0 rgba(89,105,129,.05), 0 1px 1px 0 rgba(0,0,0,.025);
    padding: 1em;"
    >



**Діаграма прецедентів**

</center>

