## TASK 1.4.4 [задание на stepik](https://stepik.org/lesson/297514/step/4?unit=279274)
Вывести информацию (автора, книгу и количество) о тех книгах, количество экземпляров которых в таблице **book** не дублируется.

**Пояснение к заданию:**

В таблице **book** в столбце **amount** хранится количество экземпляров каждой книги:

```SQL
+-----------------------+--------+
| title                 | amount |
+-----------------------+--------+
| Мастер и Маргарита    | 3      |
| Белая гвардия         | 5      |
| Идиот                 | 10     |
| Братья Карамазовы     | 3      |
| Игрок                 | 10     |
| Стихотворения и поэмы | 15     |
+-----------------------+--------+
```

В соответствии с этой таблицей:

- количество экземпляров книг "Мастер и Маргарита" и "Братья Карамазовы" одинаково и равно 3 (так как число 3 встречается в таблице два раза,
книги с таким количеством не подходят под условие);
- количество экземпляров книг "Идиот" и "Игрок" тоже одинаково и равно 10 (не подходят под условие);
- количество экземпляров книги "Белая гвардия равно" 5, при этом в таблице нет других книг, количество экземпляров которых равно 5,
следовательно, эта книга подходит под условие задачи (так как количество экземпляров 5 в таблице не дублируется);
- количество экземпляров книги "Стихотворение и поэмы"  - 15, в таблице нет других книг, количество экземпляров которых тоже равно 15,
следовательно, и эта книга подходит под условие.

Таким образом, необходимо вывести те строки таблицы, у которых числа в столбце **amount** не повторяются.

**Пояснение к решению:**

Во вложенном запросе отберите те значения столбца **amount**, количество которых, вычисленное с помощью функции ```count()```, равно 1 (единице).

**Решение:**

```SQL
SELECT author, title, amount
FROM book
WHERE amount IN (
    SELECT amount
    FROM book
    GROUP BY amount
    HAVING COUNT(*) = 1
    );
```

**Перевод на человеческий**:

```SQL
/*выбери столбцы author, title, amount*/
/*из таблицы book*/
/*выбери только те строки, в которых значения столбца amount есть в списке значений amount в результате вложенного запроса*/
/*во вложенном запросе выбери столбец amount из таблицы book, сгруппируй по столбцу amount, подсчитай сколько получилось записей в каждой группе
и выбери только те строки, в которых количество записей равно 1*/
```

**Результат**:
```SQL
+---------------+-----------------------+--------+
| author        | title                 | amount |
+---------------+-----------------------+--------+
| Булгаков М.А. | Белая гвардия         | 5      |
| Есенин С.А.   | Стихотворения и поэмы | 15     |
+---------------+-----------------------+--------+
```

**Пояснения:**

1. Нам необходимо вывести те строки таблицы, у которых числа в столбце **amount** не повторяются. Сделать это можно, подсчитав количество одинаковых
значений столбца **amount** и взять только те строки, где это количество **равно единице**. Делать это будем во вложенном запросе, в результате которого
оставим строки, где количество повторяющихся значений amount равно единице и в дальнейшем в **основном** запросе будем сравнивать значения **amount**
в основной таблице **book** со значениями **amount**, полученными в результате **вложенного** запроса.

2. Разберём сначала вложенный запрос:

Соберём в группы значения столбца **amount** с помощью оператора ```GROUP BY```:
  
```SQL
SELECT amount
FROM book
GROUP BY amount;
```

Во временной результирующей таблице получим 4 группы:
- с количеством 3
- с количеством 5
- с количеством 10
- с количеством 15

```SQL
+--------+
| amount |
+--------+
| 3      |
| 5      |
| 10     |
| 15     |
+--------+
```

Теперь к этим группам можно применить агрегирующие функции. В нашем случае мы посчитаем количество значений в каждой группе
     с помощью функции ```COUNT```.

```SQL
SELECT amount, COUNT(*)
FROM book
GROUP BY amount;
```

Получим промежуточную таблицу с результатом подсчёта (столбец ```COUNT(*)``` выведен для наглядности):

```SQL
+--------+----------+
| amount | COUNT(*) |
+--------+----------+
| 3      | 2        |
| 5      | 1        |
| 10     | 2        |
| 15     | 1        |
+--------+----------+
```

Во вложенном запросе осталось выбрать из этих строк только те, в которых ```COUNT(*)``` = 1. В выборке по условию при работе с группой
     применяем оператор ```HAVING```:

```SQL
SELECT amount
FROM book
GROUP BY amount
HAVING COUNT(*) = 1;
```

Получаем нужные нам значения, с которыми уже можно сравнивать **amount** из основого запроса:

```SQL
+--------+
| amount |
+--------+
| 5      |
| 15     |
+--------+
```

3. Можно перейти к **основному** запросу. У нас сейчас есть:

Основная таблица **book**:

```SQL
+---------+-----------------------+------------------+--------+--------+
| book_id | title                 | author           | price  | amount |
+---------+-----------------------+------------------+--------+--------+
| 1       | Мастер и Маргарита    | Булгаков М.А.    | 670.99 | 3      |
| 2       | Белая гвардия         | Булгаков М.А.    | 540.50 | 5      |
| 3       | Идиот                 | Достоевский Ф.М. | 460.00 | 10     |
| 4       | Братья Карамазовы     | Достоевский Ф.М. | 799.01 | 3      |
| 5       | Игрок                 | Достоевский Ф.М. | 480.50 | 10     |
| 6       | Стихотворения и поэмы | Есенин С.А.      | 650.00 | 15     |
+---------+-----------------------+------------------+--------+--------+
```

и список значений **amount** в результате вложенного запроса: **(5, 15)**

Осталось вывести окончательную результирующую таблицу. Для этого с помощью оператора ```WHERE``` построчно проходимся (сервер проходится) по основной таблице **book** и с помощью оператора ```IN``` сопоставляем: если значение **amount** в таблице **book** есть в значениях **amount** в результате
вложенного запроса, то добавляем такую строку в результирующую таблицу: 

```amount IN (SELECT amount FROM book GROUP BY amount HAVING COUNT(*) = 1)``` >>> ```amount IN (5, 15)```

Получаем **итоговый** результат:

```SQL
+---------------+-----------------------+--------+
| author        | title                 | amount |
+---------------+-----------------------+--------+
| Булгаков М.А. | Белая гвардия         | 5      |
| Есенин С.А.   | Стихотворения и поэмы | 15     |
+---------------+-----------------------+--------+
```
