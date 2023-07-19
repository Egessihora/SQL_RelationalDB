### Task 1.2.8 [задание на stepik](https://stepik.org/lesson/297509/step/8?unit=279269)
Вывести автора, название  и цены тех книг, количество которых меньше 10.

**Решение**:

```SQL
SELECT author, title, price    /*выбери столбцы author, title, price*/
FROM book                      /*из таблицы book*/
WHERE amount < 10;             /*выбери только те строки, где количество(amount) меньше 10*/
```
