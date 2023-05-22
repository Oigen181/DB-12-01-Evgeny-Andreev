### Задание 1 ###
---

Какие данные хранятся в этих таблицах :

1 ФИО  - фамилия имя отчество сотрудника 

2 Оклад  - заработная плата сотрудника

3 Должность  - Занимаемая должность сотрудника

4 Тип подразделения - отдел в котором работает сотрудник

5 Дата - дата найма сотрудника

6 Адрес - местонахождение филиала

7 Проект - наименование проекта для конкретного сотрудника.

---

Если данные хранятся в PostgreSQL.

1 Фио  -  строковый (varchar)

2 Оклад  - числовой (decimal/numeric)

3 Должность  - строковый (varchar)

4 Тип подразделения - строковый (varchar)

5 Дата - дата и время (tinyint)

6 Адрес - местонахождение филиала (varchar)

7 Проект - наименование проекта для конкретного сотрудника.

---
 
Проекты_имена (
- идентификатор, первичный ключ, Serial
- имя проекта varchar(150)
)

Филиалы_адреса (
- идентификатор, первичный ключ, Serial
- область_id, внешний ключ, Integer
- город_id, внешний ключ, Integer
- адрес филиала, varchar(350)
)

Области (
- идентификатор, первичный ключ, Serial
- имя района, varchar(50)
)

Города (
- идентификатор, первичный ключ, Serial
- имя города, varchar(50)
)

Подразделения_имена (
- идентификатор, первичный ключ, Serial
- имя подразделения, varchar(150)
- тип_подразделения_id, внешний ключ, Integer
)

Подразделения_типы (
- идентификатор, первичный ключ, Serial
- тип подразделения, varchar(50)
)

Должности (
- идентификатор, первичный ключ, Serial
- должность, varchar(50)
)

Сотрудники (
- идентификатор, первичный ключ, Serial
- ФИО, varchar(150)
- дата найма, DATA
- оклад, MONEY
- должность_id, внешний ключ, Integer
- подразделение_id, внешний ключ, Integer
- филиал_id, внешний ключ, Integer
)

Проекты (
- идентификатор, первичный ключ, Serial
- проект_id, внешний ключ, Integer
- сотрудник_id, внешний ключ, Integer
)

---
