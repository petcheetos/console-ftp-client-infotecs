## Тестовое задание для стажера на позицию «Автотестирование (Java)

### Задание 1
Реализован клиент для работы с FTP сервером, на котором расположен файл с информацией о студентах в виде JSON подобной структуры:
```json
{
   "students": [
      {
         "id": 1,
         "name": "Student1"
      },
      {
         "id": 2,
         "name": "Student2"
      },
      {
         "id": 3,
         "name": "Student3"
      }
   ]
}
```

Клиент разработан в виде консольного приложения, принимающего на вход логин, пароль пользователя и IP-адрес FTP-сервера. После подключение приложение принимает на вход имя файла, расположенного на сервере, и выводит меню, в котором доступны на выбор следующие действия:
1.	Получение списка студентов по имени
2.	Получение информации о студенте по id
3.	Добавление студента (id генерируется автоматически)
4.	Удаление студента по id
5.	Завершение работы
6.  Получение списка всех команд
7.  Получение отсортированного по алфавиту списка всех студентов

Целевая платформа: **Linux**

В качестве FTP-сервера используется готовое решение.

* Тестовое задание выполнено с использованием **Java SE 8**.
* Клиент умеет работать с сервером в двух режимах: активном и пассивном.
* Список студентов при выводе отсортирован по алфавиту
* id студента уникален

По умолчанию клиент работает в пассивном режиме. Использовать активный режим можно двумя способами:
1. Задать значение **false** переменной **passiveMode** в классе **ConsoleClientApplication**
2. Передать значение **false** при вызове
```java
public String getDataFromFile(String remoteFilePath, boolean passiveMode);
public boolean saveDataToFile(String data, String remoteFilePath, boolean passiveMode);
```
находящихся в класcе FTPClient. Адрес клиента в активном режиме по умолчанию задан как **127.0.0.1**, но его можно изменить в том же классе:
```java
 private final String clientIPActiveMode = "127.0.0.1";
```


