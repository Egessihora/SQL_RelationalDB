## TASK 2.2.2 [задание на stepik](https://stepik.org/lesson/308886/step/2?unit=291012)
Вывести название, жанр и цену тех книг, количество которых больше 8, в отсортированном по убыванию цены виде.

**Логическая схема базы данных:**

[![cx1.jpg](https://i.postimg.cc/gk69DKfL/cx1.jpg)](https://postimg.cc/qz0ZB2Bp)

**Решение**:

```SQL
SELECT title, name_genre, price
FROM book
    INNER JOIN genre
    ON book.genre_id = genre.genre_id
    AND amount > 8
    ORDER BY price DESC;
```

Перевод на человеческий:
```SQL
/*выбери столбцы title, name_genre, price*/
/*из таблицы book*/
/*соединённой с таблицей genre*/
/*выбери только те строки, где удовлетворяются оба условия: */
/*- book.genre_id = genre.genre_id*/
/*- количество > 8*/
/*отсортируй по цене в порядке убывания*/
```

**Результат**:
| title                 | name_genre | price  |
|-----------------------|------------|--------|
| Стихотворения и поэмы | Поэзия     | 650.00 |
| Игрок                 | Роман      | 480.50 |
| Идиот                 | Роман      | 460.00 |

Affected rows: 3
