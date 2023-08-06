## TASK 2.1.6 [задание на stepik](https://stepik.org/lesson/308885/step/6?unit=291011)
Создать таблицу **author** следующей структуры:

|Поле	       |Тип, описание                 |
|------------|------------------------------|
|author_id	 |INT PRIMARY KEY AUTO_INCREMENT|
|name_author |	VARCHAR(50)                 |

**Решение**:

```SQL
CREATE TABLE author (
    author_id INT PRIMARY KEY AUTO_INCREMENT,
    name_author VARCHAR(50)
);

DESCRIBE author;    /*DESCRIBE используется для получения информации о структуре таблицы*/
```

**Результат**:

```SQL
+-------------+-------------+------+-----+---------+----------------+
| Field       | Type        | Null | Key | Default | Extra          |
+-------------+-------------+------+-----+---------+----------------+
| author_id   | int         | NO   | PRI | NULL    | auto_increment |
| name_author | varchar(50) | YES  |     | NULL    |                |
+-------------+-------------+------+-----+---------+----------------+
Affected rows: 2
```
