## TASK 2.1.9 [задание на stepik](https://stepik.org/lesson/308885/step/9?unit=291011)
Создать таблицу **book** той же структуры, что и на предыдущем шаге. Будем считать, что при удалении автора из таблицы **author**,
должны удаляться все записи о книгах из таблицы **book**, написанные этим автором. А при удалении жанра из таблицы **genre** для
соответствующей записи **book** установить значение **Null** в столбце **genre_id**.
___
Для удаления таблицы **book**, созданной в предыдущем задании используйте следующий код:

```SQL
DROP TABLE book;
```
___
**Решение**:

```SQL
CREATE TABLE book (
book_id INT PRIMARY KEY AUTO_INCREMENT,
title VARCHAR(50),
author_id INT NOT NULL,
genre_id INT,
price DECIMAL(8,2),
amount INT,
FOREIGN KEY (author_id) REFERENCES author (author_id) ON DELETE CASCADE,
FOREIGN KEY (genre_id) REFERENCES genre (genre_id) ON DELETE SET NULL
);

DESCRIBE book;          /*DESCRIBE используется для получения информации о структуре таблицы*/
```

**Результат**:

```SQL
Query result:
+-----------+--------------+------+-----+---------+----------------+
| Field     | Type         | Null | Key | Default | Extra          |
+-----------+--------------+------+-----+---------+----------------+
| book_id   | int          | NO   | PRI | NULL    | auto_increment |
| title     | varchar(50)  | YES  |     | NULL    |                |
| author_id | int          | NO   | MUL | NULL    |                |
| genre_id  | int          | YES  | MUL | NULL    |                |
| price     | decimal(8,2) | YES  |     | NULL    |                |
| amount    | int          | YES  |     | NULL    |                |
+-----------+--------------+------+-----+---------+----------------+
Affected rows: 6
```
