# Домашнее задание по теме "Введение в SQL. Установка ПО"

### Задание

Вопросы по заданию
Преподаватель: Николай Хащанов, Игорь Крамер
Все работы мы проверяем на антиплагиат, поэтому важно выполнять их самостоятельно. Работам, которые не пройдут проверку, преподаватель поставит незачёт. Если вы сталкиваетесь со сложностями, задавайте вопросы нашим экспертам и аспирантам, они с удовольствием вам помогут. Успехов в решении заданий!

## Модуль 1. Домашнее задание по теме «Введение в SQL и установка ПО»

Цель домашнего задания:

_научиться настраивать подключение к базе данных_

_научиться формировать ER-диаграмму таблиц базы данных_

_закрепить знания по определению первичных ключей для таблиц_

_написать и выполнить первый SQL-запрос_

## Перечень заданий

Важно: Если вы изначально установили локальный сервер, то дополнительно создавать облачное подключение в этом задании не обязательно. Выполните задания 2–4 из основной части на локальной базе данных.

### Основная часть:

### Задание 1.
Создайте новое соединение в DBeaver и подключите облачную базу данных с учебной базой данных dvd-rental согласно инструкции. Сделайте скриншот результата.

![](./scrs/connect_to_cloud_db_pgsql.png)

![](./scrs/test_connection_to_cloud_db_pgsql.png)

### Задание 2.
Откройте ER-диаграмму таблиц учебной базы данных dvd-rental. Сделайте скриншот результата.

![](./scrs/ERD.png)

### Задание 3.
Перечислите все таблицы учебной базы данных dvd-rental и столбцы, которые имеют ограничения первичных ключей для этих таблиц. Запишите решение в формате таблицы: letsdocode.ru...in/1-3.png

```sql
SELECT
	  tc.table_name AS "Название таблицы"
	, tc.constraint_name AS "Поле таблицы"
FROM
	information_schema.table_constraints tc
WHERE
	tc.constraint_type = 'PRIMARY KEY'
;
```

Вывод результата запроса:

|Название таблицы|Поле таблицы|
|----------------|------------|
|actor|actor_pkey|
|address|address_pkey|
|category|category_pkey|
|city|city_pkey|
|country|country_pkey|
|customer|customer_pkey|
|film_actor|film_actor_pkey|
|film_category|film_category_pkey|
|film|film_pkey|
|inventory|inventory_pkey|
|language|language_pkey|
|payment|payment_pkey|
|rental|rental_pkey|
|staff|staff_pkey|
|store|store_pkey|

![](./scrs/sql_request_0.png)

<!--

|No.|Название таблицы|Поле таблицы, которое является первичным ключом|
|---|---|---|
|1|payment|payment_id|
|2|rental|rental_id|
|3|customer|customer_id|
|4|store|store_id|
|5|staff|staff_id|
|5|address|address_id|
|7|city|city_id|
|8|country|country_id|
|9|inventory|inventory_id|
|10|actor|actor_id|
|11|film_actor|actor_id, film_id|
|12|film|film_id|
|13|language|language_id|
|14|category|category_id|
|15|film_category|film_id, category_id|

-->

### Задание 4.
Выполните SQL-запрос к учебной базе данных dvd-rental “SELECT * FROM country;”. Сделайте скриншот результата.

Ожидаемый результат запроса: letsdocode.ru...in/1-4.png


Выполнение запроса:

```sql
SELECT * 
FROM country
;
```

Результат запроса:

![](./scrs/sql_request_1.png)


<details>
  <summary>
  
  Вывод результата запроса

  </summary>

|country_id|country|last_update|
|----------|-------|-----------|
|1|Afghanistan|2006-02-15 04:44:00.000|
|2|Algeria|2006-02-15 04:44:00.000|
|3|American Samoa|2006-02-15 04:44:00.000|
|4|Angola|2006-02-15 04:44:00.000|
|5|Anguilla|2006-02-15 04:44:00.000|
|6|Argentina|2006-02-15 04:44:00.000|
|7|Armenia|2006-02-15 04:44:00.000|
|8|Australia|2006-02-15 04:44:00.000|
|9|Austria|2006-02-15 04:44:00.000|
|10|Azerbaijan|2006-02-15 04:44:00.000|
|11|Bahrain|2006-02-15 04:44:00.000|
|12|Bangladesh|2006-02-15 04:44:00.000|
|13|Belarus|2006-02-15 04:44:00.000|
|14|Bolivia|2006-02-15 04:44:00.000|
|15|Brazil|2006-02-15 04:44:00.000|
|16|Brunei|2006-02-15 04:44:00.000|
|17|Bulgaria|2006-02-15 04:44:00.000|
|18|Cambodia|2006-02-15 04:44:00.000|
|19|Cameroon|2006-02-15 04:44:00.000|
|20|Canada|2006-02-15 04:44:00.000|
|21|Chad|2006-02-15 04:44:00.000|
|22|Chile|2006-02-15 04:44:00.000|
|23|China|2006-02-15 04:44:00.000|
|24|Colombia|2006-02-15 04:44:00.000|
|25|Congo, The Democratic Republic of the|2006-02-15 04:44:00.000|
|26|Czech Republic|2006-02-15 04:44:00.000|
|27|Dominican Republic|2006-02-15 04:44:00.000|
|28|Ecuador|2006-02-15 04:44:00.000|
|29|Egypt|2006-02-15 04:44:00.000|
|30|Estonia|2006-02-15 04:44:00.000|
|31|Ethiopia|2006-02-15 04:44:00.000|
|32|Faroe Islands|2006-02-15 04:44:00.000|
|33|Finland|2006-02-15 04:44:00.000|
|34|France|2006-02-15 04:44:00.000|
|35|French Guiana|2006-02-15 04:44:00.000|
|36|French Polynesia|2006-02-15 04:44:00.000|
|37|Gambia|2006-02-15 04:44:00.000|
|38|Germany|2006-02-15 04:44:00.000|
|39|Greece|2006-02-15 04:44:00.000|
|40|Greenland|2006-02-15 04:44:00.000|
|41|Holy See (Vatican City State)|2006-02-15 04:44:00.000|
|42|Hong Kong|2006-02-15 04:44:00.000|
|43|Hungary|2006-02-15 04:44:00.000|
|44|India|2006-02-15 04:44:00.000|
|45|Indonesia|2006-02-15 04:44:00.000|
|46|Iran|2006-02-15 04:44:00.000|
|47|Iraq|2006-02-15 04:44:00.000|
|48|Israel|2006-02-15 04:44:00.000|
|49|Italy|2006-02-15 04:44:00.000|
|50|Japan|2006-02-15 04:44:00.000|
|51|Kazakstan|2006-02-15 04:44:00.000|
|52|Kenya|2006-02-15 04:44:00.000|
|53|Kuwait|2006-02-15 04:44:00.000|
|54|Latvia|2006-02-15 04:44:00.000|
|55|Liechtenstein|2006-02-15 04:44:00.000|
|56|Lithuania|2006-02-15 04:44:00.000|
|57|Madagascar|2006-02-15 04:44:00.000|
|58|Malawi|2006-02-15 04:44:00.000|
|59|Malaysia|2006-02-15 04:44:00.000|
|60|Mexico|2006-02-15 04:44:00.000|
|61|Moldova|2006-02-15 04:44:00.000|
|62|Morocco|2006-02-15 04:44:00.000|
|63|Mozambique|2006-02-15 04:44:00.000|
|64|Myanmar|2006-02-15 04:44:00.000|
|65|Nauru|2006-02-15 04:44:00.000|
|66|Nepal|2006-02-15 04:44:00.000|
|67|Netherlands|2006-02-15 04:44:00.000|
|68|New Zealand|2006-02-15 04:44:00.000|
|69|Nigeria|2006-02-15 04:44:00.000|
|70|North Korea|2006-02-15 04:44:00.000|
|71|Oman|2006-02-15 04:44:00.000|
|72|Pakistan|2006-02-15 04:44:00.000|
|73|Paraguay|2006-02-15 04:44:00.000|
|74|Peru|2006-02-15 04:44:00.000|
|75|Philippines|2006-02-15 04:44:00.000|
|76|Poland|2006-02-15 04:44:00.000|
|77|Puerto Rico|2006-02-15 04:44:00.000|
|78|Romania|2006-02-15 04:44:00.000|
|79|Runion|2006-02-15 04:44:00.000|
|80|Russian Federation|2006-02-15 04:44:00.000|
|81|Saint Vincent and the Grenadines|2006-02-15 04:44:00.000|
|82|Saudi Arabia|2006-02-15 04:44:00.000|
|83|Senegal|2006-02-15 04:44:00.000|
|84|Slovakia|2006-02-15 04:44:00.000|
|85|South Africa|2006-02-15 04:44:00.000|
|86|South Korea|2006-02-15 04:44:00.000|
|87|Spain|2006-02-15 04:44:00.000|
|88|Sri Lanka|2006-02-15 04:44:00.000|
|89|Sudan|2006-02-15 04:44:00.000|
|90|Sweden|2006-02-15 04:44:00.000|
|91|Switzerland|2006-02-15 04:44:00.000|
|92|Taiwan|2006-02-15 04:44:00.000|
|93|Tanzania|2006-02-15 04:44:00.000|
|94|Thailand|2006-02-15 04:44:00.000|
|95|Tonga|2006-02-15 04:44:00.000|
|96|Tunisia|2006-02-15 04:44:00.000|
|97|Turkey|2006-02-15 04:44:00.000|
|98|Turkmenistan|2006-02-15 04:44:00.000|
|99|Tuvalu|2006-02-15 04:44:00.000|
|100|Ukraine|2006-02-15 04:44:00.000|
|101|United Arab Emirates|2006-02-15 04:44:00.000|
|102|United Kingdom|2006-02-15 04:44:00.000|
|103|United States|2006-02-15 04:44:00.000|
|104|Venezuela|2006-02-15 04:44:00.000|
|105|Vietnam|2006-02-15 04:44:00.000|
|106|Virgin Islands, U.S.|2006-02-15 04:44:00.000|
|107|Yemen|2006-02-15 04:44:00.000|
|108|Yugoslavia|2006-02-15 04:44:00.000|
|109|Zambia|2006-02-15 04:44:00.000|

</details>

### Дополнительная часть:

### Задание 1.
Установите локальный сервер PostgreSQL, восстановите учебные данные согласно инструкции и повторите задания 2–4 из основной части домашнего задания на локальной базе данных. Сделайте все необходимые скриншоты. Если вы изначально установили локальный сервер, то можете сразу приступать к следующему заданию.

Локальная СУБД установлена на ОС Linux. 

![](./scrs/connect_to_local_db_pgsql.png)

![](./scrs/test_connection_to_local_db_pgsql.png)

### Задание 2.
С помощью SQL-запроса выведите в результат таблицу, содержащую названия таблиц и названия ограничений первичных ключей в этих таблицах. Для написания запроса используйте представление information_schema.table_constraints.

```sql
SELECT 
	  tc.table_name AS "Table Name" 
	, kc.column_name AS "Column Name"
	, tc.constraint_name AS "Constraint Name" 
	, tc.constraint_type AS "Constraint Type"
	, c.data_type AS "Data Type"
FROM 
	information_schema.table_constraints tc
  INNER JOIN information_schema.key_column_usage kc 
    ON kc.table_name = tc.table_name and kc.table_schema = tc.table_schema and kc.constraint_name = tc.constraint_name
      JOIN information_schema.columns c 
	ON c.column_name = kc.column_name and c.table_schema = kc.table_schema 
WHERE 
	tc.constraint_type = 'PRIMARY KEY'
ORDER BY 
	tc.table_name
;
```

![](./scrs/sql_request_2.png)


<details>
  <summary>

  Вывод результата запроса

  </summary>

|Table Name|Column Name|Constraint Name|Constraint Type|Data Type|
|----------|-----------|---------------|---------------|---------|
|actor|actor_id|actor_pkey|PRIMARY KEY|smallint|
|actor|actor_id|actor_pkey|PRIMARY KEY|integer|
|actor|actor_id|actor_pkey|PRIMARY KEY|integer|
|address|address_id|address_pkey|PRIMARY KEY|smallint|
|address|address_id|address_pkey|PRIMARY KEY|smallint|
|address|address_id|address_pkey|PRIMARY KEY|smallint|
|address|address_id|address_pkey|PRIMARY KEY|integer|
|category|category_id|category_pkey|PRIMARY KEY|integer|
|category|category_id|category_pkey|PRIMARY KEY|smallint|
|city|city_id|city_pkey|PRIMARY KEY|smallint|
|city|city_id|city_pkey|PRIMARY KEY|integer|
|country|country_id|country_pkey|PRIMARY KEY|smallint|
|country|country_id|country_pkey|PRIMARY KEY|integer|
|customer|customer_id|customer_pkey|PRIMARY KEY|integer|
|customer|customer_id|customer_pkey|PRIMARY KEY|smallint|
|customer|customer_id|customer_pkey|PRIMARY KEY|smallint|
|film|film_id|film_pkey|PRIMARY KEY|integer|
|film|film_id|film_pkey|PRIMARY KEY|smallint|
|film|film_id|film_pkey|PRIMARY KEY|smallint|
|film|film_id|film_pkey|PRIMARY KEY|smallint|
|film_actor|film_id|film_actor_pkey|PRIMARY KEY|smallint|
|film_actor|film_id|film_actor_pkey|PRIMARY KEY|smallint|
|film_actor|film_id|film_actor_pkey|PRIMARY KEY|smallint|
|film_actor|actor_id|film_actor_pkey|PRIMARY KEY|integer|
|film_actor|actor_id|film_actor_pkey|PRIMARY KEY|smallint|
|film_actor|actor_id|film_actor_pkey|PRIMARY KEY|integer|
|film_actor|film_id|film_actor_pkey|PRIMARY KEY|integer|
|film_category|category_id|film_category_pkey|PRIMARY KEY|smallint|
|film_category|film_id|film_category_pkey|PRIMARY KEY|integer|
|film_category|film_id|film_category_pkey|PRIMARY KEY|smallint|
|film_category|film_id|film_category_pkey|PRIMARY KEY|smallint|
|film_category|film_id|film_category_pkey|PRIMARY KEY|smallint|
|film_category|category_id|film_category_pkey|PRIMARY KEY|integer|
|inventory|inventory_id|inventory_pkey|PRIMARY KEY|integer|
|inventory|inventory_id|inventory_pkey|PRIMARY KEY|integer|
|language|language_id|language_pkey|PRIMARY KEY|smallint|
|language|language_id|language_pkey|PRIMARY KEY|integer|
|payment|payment_id|payment_pkey|PRIMARY KEY|integer|
|rental|rental_id|rental_pkey|PRIMARY KEY|integer|
|rental|rental_id|rental_pkey|PRIMARY KEY|integer|
|staff|staff_id|staff_pkey|PRIMARY KEY|smallint|
|staff|staff_id|staff_pkey|PRIMARY KEY|smallint|
|staff|staff_id|staff_pkey|PRIMARY KEY|integer|
|store|store_id|store_pkey|PRIMARY KEY|smallint|
|store|store_id|store_pkey|PRIMARY KEY|smallint|
|store|store_id|store_pkey|PRIMARY KEY|smallint|
|store|store_id|store_pkey|PRIMARY KEY|integer|

</details>


Результат домашнего задания
В качестве ответов на основную часть необходимо прикрепить скриншот на каждый пункт задания.
В качестве ответов на дополнительную часть необходимо прислать скриншоты по заданию 1 и sql-файл с запросом по заданию 2.

Критерии оценки
Для получения зачета по этому домашнему заданию необходимо правильно выполнить все задания из основной части.

Преподаватель вправе предложить дополнительные задачи в рамках задания, чтобы подтвердить, что студент разобрался в теме.
Преподаватель вправе поставить незачет без права пересдачи текущего задания, если студент прислал на проверку результат чужой работы и отказался делать дополнительное задание.

### Результат проверки

![](./scrs/result_module1.png)
