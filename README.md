### Домашнее задание к занятию «Базы данных» - "Сергей Шульга"

#### Задание 1
#### Опишите не менее семи таблиц, из которых состоит база данных:
#### какие данные хранятся в этих таблицах;
1. Ф.И.О.;
2. Оклад;
3. Должность;
4. Тип подразделения;
5. Структурное подразделение;
6. Дата найма;
7. Адрес филиала;
8. Проект на который назначен.

#### какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.
1. Ф.И.О - cимвольный тип (varchar/text)
2. Оклад - типы для работы с валютой (денежными единицами) (money)
3. Должность - символьный тип (varchar/text)
4. Тип подразделения - символьный тип (varchar/text)
5. Структурное подразделение - символьный тип (varchar/text)
6. Дата найма - типы для работы с датами и временем (timestamp)
7. Адрес филиала - символьный тип (varchar/text)
8. Проект - символьный тип (varchar/text)

#### Приведите решение к следующему виду:

Сотрудники (
идентификатор, первичный ключ, serial,
фамилия varchar(50),
...
идентификатор структурного подразделения, внешний ключ, integer).

staff (
staff_id primary_key,
FName VARCHAR(50) ,
LName VARCHAR(50) ,
Patronymic varchar(50),
divisions_id varchar(50),
Structura_id varchar(50),
date_off_id datetime,
position_id varchar(50),
salary_id numeric,
address_id VARCHAR(50),
project_id VARCHAR(50),
)

salary (
salary_id primary_key
pay numeric
)

position (
position_id primary_key
spethion_type
)

divisions (
divisions_id primary_key
department varchar(50)
Unit Group varchar(50)
Unit Group_type
department_type
)

Structura (
Structura_id primary_key
Group varchar(50)
Structura_type
Structura_title
)

date_off_Employee )
date_off_id primary_key
date datetime
)

branch address (
address_id primary_key
edge VARCHAR(50)
city VARCHAR(50)
street VARCHAR(50)
house VARCHAR(50)
)

project (

project_id primary_key

project_type

)


Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.

Задание 2*
Перечислите, какие, на ваш взгляд, в этой денормализованной таблице встречаются функциональные зависимости и какие правила вывода нужно применить, чтобы нормализовать данные.
