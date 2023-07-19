### Task 1.1.8 [задание на stepik](https://stepik.org/lesson/297508/step/8?unit=279268)
Сформулируйте SQL запрос для создания таблицы **book**.

Структура таблицы **book**:

| Поле  | Тип, описание                |
|-------|------------------------------|
|book_id|INT PRIMARY KEY AUTO_INCREMENT|
|title  |VARCHAR(50)                   |
|author |VARCHAR(30)                   |
|price  |DECIMAL(8, 2)                 |
|amount |INT                           |

**Пояснение**: *При записи сохраняйте порядок следования полей.*

**Решение**:
```sql 
CREATE TABLE book(                              /*Создать таблицу с именем book*/
    book_id INT PRIMARY KEY AUTO_INCREMENT,     /*Столбец book_id целое число атоматическое заполнение*/
    title VARCHAR(50),                          /*Столбец title строка до 50 символов*/
    author VARCHAR(30),                         /*Столбец author строка до 30 символов*/
    price DECIMAL(8, 2),                        /*Столбец price число до 8 символов 2 из них дробь*/
    amount INT);                                /*Столбец amount целое число*/
```
