## Установка MySQL-сервера

* Linux

sudo apt-get update

sudo apt-get install mysql-server

* Windows 10

Процесс установки MySQL-сервера версии 8.0 на Windows 10 с помощью автоматического установщика.
1. Автоматический установщик необходимо скачать по [следующей ссылке](https://dev.mysql.com/get/Downloads/MySQLInstaller/mysql-installer-community-8.0.11.0.msi).
В нём уже есть всё необходимое для установки.

2. Дважды кликаем на исполняемый файл, принимаем условия лицензионного соглашения (галочка) и кликаем Next.

[![1.png](https://i.postimg.cc/5tR79qkP/1.png)](https://postimg.cc/2qnF2vYv)

3. Выбираем тип установки, коих есть несколько - установка готового "набора разработчика", установка только сервера, только клиента, полная установка (первая опция + дополнительные инструменты) и кастомная. В нашем случае мы выбираем установку сервера.

[![2.png](https://i.postimg.cc/rm2htFMW/2.png)](https://postimg.cc/wtF5CztT)

4. Кликаем Execute и ждём завершения установки.

[![3.png](https://i.postimg.cc/8P7hNgVV/3.png)](https://postimg.cc/vcd1tjBP)

5. Нажимаем Next.

[![4.png](https://i.postimg.cc/cJLwHvK6/4.png)](https://postimg.cc/fV1JqTfh)

6. Переходим на этап настройки - нажимаем Next.

[![5.png](https://i.postimg.cc/ZKJRZ1v5/5.png)](https://postimg.cc/qgZ0xDGP)

7. Для самой простой установки, выбираем первую опцию, также как на скриншоте - отдельный MySQL сервер и кликаем Next.

[![6.png](https://i.postimg.cc/QM3Ynknw/6.png)](https://postimg.cc/w1wk1JzQ)

8. Настраиваем сетевые параметры - можно оставить по умолчанию.

[![7.png](https://i.postimg.cc/zvgPct8m/7.png)](https://postimg.cc/2LCwqx1T)

9. Затем настраиваем параметры аутентификации - выбираем первую опцию и нажимаем Next.

[![8.png](https://i.postimg.cc/HkpBwsc1/8.png)](https://postimg.cc/0bBYxv0V)

10. Устанавливаем рутовый пароль для сервера - чем сложнее, тем лучше. Рекомендуется использовать по меньшей мере пароль из 12 символов, содержащий буквы, цифры и специальные символы. Также на этом этапе можно добавить пользователей.

[![9.png](https://i.postimg.cc/HkcjPb7w/9.png)](https://postimg.cc/jDTsDwc2)

11. Настраиваем свойства службы MySQL - указываем имя службы, параметры автозапуска и из под какой учетной записи необходимо запускать данную службу.

[![10.png](https://i.postimg.cc/yxx73zmm/10.png)](https://postimg.cc/gXCC1QBj)

12. Настраиваем плагины и расширения или оставить всё по умолчанию.

[![11.png](https://i.postimg.cc/X7FYfnML/11.png)](https://postimg.cc/Yhr7kKCL)

13. Далее необходимо применить настройки - кликаем Execute и ждём.

[![12.png](https://i.postimg.cc/jjkTV10C/12.png)](https://postimg.cc/ns7gB0Lt)

14. Готово! Установка завершена. Теперь осталось нажать Finish два раза - поздравляю! Вы установили MySQL-сервер.

[![13.png](https://i.postimg.cc/J7NFZF6J/13.png)](https://postimg.cc/V5N4cKcL)

15. Теперь можно проверить его работоспособность. Для этого необходимо открыть приложение, которое было установлено вместе с сервером - MySQL 8.0 Command Line Client. Необходимо будет ввести рутовый пароль, который был указан вами во время установки и, затем, выполнить команду show databases;

*Очень важно не забывать точку с запятой в командах, как в примере выше!*

Результатом вы должны увидеть несколько созданных по умолчанию баз данных - mysql, performance_schema, information_schema и sys. Для выхода введите команду exit.

[![14.png](https://i.postimg.cc/C5XbxQmc/14.png)](https://postimg.cc/LgkJyNdP)
