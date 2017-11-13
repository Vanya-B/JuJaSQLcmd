SQLcmd консольная программа для работы с базон данных.

   База данных : PostgreSQL

Для начала работы :
 - установите PostgreSQL server;
 - создайте базу данных и пользователя этой базы;
 - в файле "SQLcmd/src/main/resources/connection.properties" укажите свои host, port, schema.
 - для тестов в файле "SQLcmd/src/test/resources/connection.properties" укажите host, port, userName, password, dataBaseName, schemaName.

6u [Подключение к базе] Я как ЮЗЕР хочу подключиться к существующей базе данных и вносить в нее правки
   * 6u.1 [Успешно подключились] я вижу приветствие от программы -> я ввожу имя базы, юзер, пароль -> я вижу сообщение что все ок (подключение успешно) -> PROFIT;
   * 6u.2 [Неправильный пароль] я вижу приветствие от программы -> я ввожу имя базы, юзер, пароль (не верный) -> я вижу сообщение, что пароль не правильный -> я вижу поле для повторного ввода пароля -> я ввожу его (правильный) -> подключение успешно -> ПРОФИТ
    * 6u.3 [Несуществующая база] приветствие -> ввожу имя несуществующей базы c какими-то логином и паролем -> вижу что базы не существует -> повторное поле ввода -> ввожу все правильно -> подключился
    * 6u.4 [Несуществующий пользователь] приветствие -> ввожу имя несуществующего пользователя и паролем -> вижу что пользователя не существует -> повторное поле ввода -> ввожу все правильно -> подключился
    
5u [Создаиие базы данных] Я как ЮЗЕР хочу иметь возможность создавать базу данных для работы с ней
   * 5u.1 [Создание новой БД] Вижу поле для ввода -> Ввожу команду "createDatabase|databaseName" -> вижу сообщение об удачном создании ,базы данных;
   * 5u.2 [Создание существующей БД] Вижу поле для ввода -> Ввожу команду "createDatabase|existDatabaseName"-> вижу сообщение об ошибке;
   
10u [Удаление базы данных] Я как ЮЗЕР хочу иметь возможность удалять базу данных 
   * 10u.1 [Удаление БД] Вижу поле для ввода -> Ввожу команду "dropDatabase|databaseName" -> вижу сообщение об удачном удалении базы данных;
   * 10u.2 [Удаление несуществующей БД] Вижу поле для ввода -> Ввожу команду "dropDatabase|unexistDatabaseName"-> вижу сообщение об ошибке;
   
10x [Список баз данных] Я как ЮЗЕР хочу, чтобы у меня было видно список всех баз данных, для того, чтобы иметь возможность с ними работать
   * 10x.1 [Вывод баз данных] Вижу поле для ввода -> Ввожу команду "databases" -> вижу список баз данных в формате "[databaseName1, databaseName2, databaseName3]"
   * 10x.2 [Ошибочная команда] Вижу поле для ввода -> Ввожу неправильную команду "databaseBUG" -> вижу сообщение об ошибке, что такой команды не существует -> вижу поле для ввода

7a [Создание схемы] Я как ЮЗЕР хочу иметь возможность создавать схему для работы с ней
   * 7a.1 [Создание новой схемы] Вижу поле для ввода -> Ввожу команду "createSchema|schemaName -> вижу сообщение об удачном создании cхемы;
   * 7a.2 [Создание существующей схемы] Вижу поле для ввода -> Ввожу команду "createSchema|existSchemaName -> вижу сообщение об ошибке;

1x [Список схем] Я как ЮЗЕР хочу, чтобы у меня было видно список всех схем, для того, чтобы иметь возможность с ними работать
   * 1x.1 [Вывод схем] Вижу поле для ввода -> Ввожу команду "schemas" -> вижу список схем в формате "[schemaName1, schemaName2, schemaName3]"
   * 1x.2 [Ошибочная команда] Вижу поле для ввода -> Ввожу неправильную команду "schemasBUG" -> вижу сообщение об ошибке, что такой команды не существует -> вижу поле для ввода

2x [Выбор схемы] Я как ЮЗЕР хочу, чтобы я мог менять схемы , для того, чтобы иметь возможность с ними работать
   * 2x.1 [Выбор схемы по имени] Вижу поле для ввода -> Ввожу команду "selectSchema|schemaName" -> вижу сообщение об удачном выборе схемы;
   * 2x.2 [Выбор несуществующей схемы] Вижу поле для ввода -> Ввожу неправильное имя схемы "selectSchema|schemaInvalidName" -> вижу сообщение об ошибке, что такой схемы нет -> вижу поле для ввода

5t [Создание таблицы] Я как ЮЗЕР хочу иметь возможность создавать таблицу для работы с ней
   * 5t.1 [Создание таблицы с именем и колонками] Вижу поле для ввода -> Ввожу команду "create|tableName|column|...|columnN" -> вижу сообщение об удачном создании таблицы и имя таблицы;
   * 5t.2 [Создание таблицы с неправильным количеством параметров] Вижу поле для ввода -> Ввожу команду "create|tableName" -> вижу сообщение об ошибке -> вижу поле для ввода команды;
   * 5t.3 [Создание таблицы с неправильным форматом имени колонки] Вижу поле для ввода команды -> Ввожу команду "create|tableName|wrongColumn" -> вижу сообщение об ошибке -> вижу поле для ввода команды;

4r [Список таблиц] Я как ЮЗЕР хочу, чтобы у меня было видно список всех таблиц, для того, чтобы иметь возможность с ними работать
   * 4r.1 [Вывод таблиц] Вижу поле для ввода -> Ввожу команду "list" -> вижу список таблиц в формате "[tableName1, tableName2, tableName3]"
   * 4r.2 [Ошибочная команда] Вижу поле для ввода -> Ввожу неправильную команду "lisBUGt" -> вижу сообщение об ошибке, что такой команды не существует -> вижу поле для ввода
    
3e [Содержимое таблицы] Я как ЮЗЕР хочу, иметь возможность просмотреть содержимое таблицы перед правкой.
   * 3e.1 [Вывод содержимого таблицы] Вижу поле для ввода -> Ввожу команду "find tableName1" -> вижу список всех данных таблицы, в формате текстовой таблички -> вижу поле для ввода команды
   * 3e.1 [Таблицы не существует] Вижу поле для ввода -> Ввожу команду "find NOTEXISTStable" -> вижу сообщение о том, что таблицы не найдено -> вижу список всех таблиц -> вижу поле для ввода команды
   * 3e.1 [Вывод части таблицы] Вижу поле для ввода -> Ввожу команду "find tableName1 LIMIT OFFSET" -> вижу список записей этой странички, в формате текстовой таблички -> вижу поле для ввода команды
    
6m [Изменение таблицы] Я как ЮЗЕР хочу иметь возможность править конкретную запись в таблице
   * 6m.1 [Изменение строки таблицы по 'id'] Вижу поле для ввода -> Ввожу команду "update|tableName|id|column|value|columnN|valueN" -> вижу список записей, в формате текстовой таблички с новыми значениями -> вижу поле для ввода команды
   * 6m.2 [Неверный параметр] Вижу поле для ввода -> Ввожу команду с неверным id (tableName, column...) -> вижу сообщение о том ,что один с параметров неверный -> вижу поле для ввода команды

7d [Очистка таблицы] Я как ЮЗЕР хочу иметь возможность очищать конкретную таблицу
   * 7d.1 [Очистка таблицы по имени] Вижу поле для ввода команды -> ввожу clean|tableName -> виже текстовое подтверждение очистки и таблицу;
   * 7d.2 [Очистка не существующей таблицы] Вижу поле для ввода команды -> ввожу clean|wrongTableName -> виже сообщение об ошибке -> вижу поле для ввода команды;
   
7g [Удаление таблицы] Я как ЮЗЕР хочу иметь возможность удалять конкретную таблицу
   * 7g.1 [Удаление таблицы по ммени] Вижу поле для ввода команды -> ввожу drop|tableName -> виже текстовое подтверждение удаления;
   * 7g.2 [Удаление не существующей таблицы] Вижу поле для ввода команды -> ввожу drop|wrongTableName -> вижу сообщение об ошибке -> вижу поле для ввода команды;
   
6h [Вставка в таблицу] Я как ЮЗЕР хочу иметь возможность вносить данные в таблицу
   * 6h.1 [Вставка данных в таблицу] Вижу поле для ввода команды -> ввожу insert|tableName|column1|value1|column2|value2|columnN|valueN... -> вижу текстовое сообщение об успешном добавлении данных;
   * 6h.2 [Вставка данных в таблицу с неверными параметрами] Вижу поле для ввода команды -> ввожу insert|wrongTableName|wrongColumn1|value1|column2|value2|columnN|valueN... -> вижу текстовое сообщение об ошибке -> вижу поле ввода команды;
   
9d [Запуск query] Я как ЮЗЕР хочу иметь возможность выполнять соответствующие QUERY для того, чтобы проверять их или выбирать конкретные значения.
