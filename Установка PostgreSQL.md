## Установка PostgreSQL
1. Для установки необходимо перейти на [официальный сайт](https://www.postgresql.org/download/) и скачать подходящую версию (лучше всего использовать свежую версию, но не бета).

[![install-1.png](https://i.postimg.cc/tC4rK4kR/install-1.png)](https://postimg.cc/dDgmdvgg)

2.
[![install-2.png](https://i.postimg.cc/kM1NtFN9/install-2.png)](https://postimg.cc/6TZ4kZ11)

3.
[![install-3.png](https://i.postimg.cc/dVdGXbbt/install-3.png)](https://postimg.cc/k2JVRpMk)

4.
[![install-4.png](https://i.postimg.cc/1Rj6zRP3/install-4.png)](https://postimg.cc/HjbjZgVq)

5. Укажите пароль к вашей БД:

[![install-5.png](https://i.postimg.cc/FKTVv2Zt/install-5.png)](https://postimg.cc/5HFCqKTp)

6. Порт оставляем по-умолчанию:

[![install-6.png](https://i.postimg.cc/yxHdbNZ7/install-6.png)](https://postimg.cc/LYx2q2DW)

7.
[![install-7.png](https://i.postimg.cc/XqsbkNKH/install-7.png)](https://postimg.cc/xNNh024M)

8. Соглашаемся со всеми предложенными настройками и снова нажимаем Next:

[![install-8.png](https://i.postimg.cc/bNZMBRqN/install-8.png)](https://postimg.cc/1fZJgwgL)

9. После того, как установка закончилась, необходимо проверить, что всё прошло удачно. Для этого нужно подключиться к базе данных с помощью встроенной утилиты SQL Shell (psql), которая устанавливается вместе с PostgreSQL. Это можно сделать двумя способами:
    * зайти в папку bin в директории, в которую производилась установка PostgreSQL, и запустить psql.exe
    * в поиске: нажать кнопку Windows и ввести нужную программу —  psql.

После запуска программы откроется консоль и вам необходимо будет ввести параметры для подключения к базе данных: адрес сервера, имя базы, порт, имя пользователя и пароль. Вы можете ввести свои параметры, если они были настроены при установке БД, или выбрать параметры по-умолчанию (отображаются в квадратных скобках), нажав Enter.

***Обратите внимание, что пароль должен совпадать с тем, который вы указывали при установке.***

Теперь вы подключились к базе данных и можете выполнять запросы. На скриншоте ниже в качестве примера выполнен запрос версии программы:

[![SQL-shell.png](https://i.postimg.cc/3xKxDZV1/SQL-shell.png)](https://postimg.cc/hf5BkVSQ)
