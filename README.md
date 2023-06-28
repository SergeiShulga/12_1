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

Отношение "Сотрудники" (
Идентификатор serial первичный ключ,
ФИО varchar (150) not null,

Оклад int not null,

Идентификатор должности smallint not null, ссылается на атрибут "Идентификатор" отношения "Должности",

Идентификатор филиала smallint not null, ссылается на атрибут "Идентификатор" отношения "Филиалы".

Отношение " Должности"
Идентификатор serial первичный ключ,
Наименование varchar (100) not null.

Отношение "Тип подразделения"
Идентификатор serial первичный ключ,
Наименование varchar(50) not null.

Отношение "Структурное подразделение"
Идентификатор serial первичный ключ,
Наименование varchar (100) not null.

Отношение "Сотрудник_Тип подразделения_Структурное подразделение"
Идентификатор сотрудника int not null, ссылается на арибут "Идентификатор" отношения "Сотрудники",
Идентификатор типа подразделения smallint not null, ссылается на атрибут "Идентификатор" отношения "Тип подразделения".
Идентификатор структурного подразделения smallint not null, ссылается на атрибут "Идентификатор" отношения "Структурное подразделение",

дата найма (приема/перевода) date not null,
дата перевода/увольнения date.

Отношение "Филиалы"
Идентификатор serial первичный ключ,
Идентификатор города int not null, ссылается на атрибут "Идентификатор" отношения "Город",
Идентификатор области int not null, ссылается на атрибут "Идентификатор" отношения "Область"
Адрес varchar(200) not null.

Отношение "Город"
Идентификатор serial первичный ключ,
Наименование varchar(100) not null
Идентификатор области int not null, ссылается на атрибут "Идентификатор" отношения "Область".

Отношение "Область"
Идентификатор serial первичный ключ,
Наименование varchar(200) not null.

Отношение "Проект"
Идентификатор serial первичный ключ,
Наименование varchar(200) not null.

Отношение "Сотрудник_Проект" может быть многие ко многим
Идентификатор сотрудника int not null, ссылается на атрибут "Идентификатор" отношения "Сотрудники",

Идентификатор проекта int not null, ссылается на атрибут "Идентификатор" отношения "Проект".
