[![Build status](https://ci.appveyor.com/api/projects/status/i7moncd4j2uhjg7v/branch/main?svg=true)](https://ci.appveyor.com/project/Mariyam197/patterntask2/branch/main)



* **Время, затраченное на ручное тестирование (минут):** 120;
* **Время, затраченное на автоматизацию (минут):** 300.

# Домашнее задание к занятию «2.3. Patterns»

## Задача №2: тестовый режим

Разработчики интернет-банка, изрядно поворчав, предоставили вам тестовый режим запуска целевого сервиса, в котором открыта программная возможность создания клиентов банка, чтобы вы могли протестировать хотя бы функцию входа.

Важно: ваша задача заключается в том, чтобы протестировать функцию входа через веб-интерфейс с использованием Selenide.

Для удобства вам предоставили документацию, которая описывает возможность программного создания клиентов банка через API. Вот дословно представленное ими описание:

    Для создания клиента нужно делать запрос вида:

    POST /api/system/users
    Content-Type: application/json

    {
         "login": "vasya",
         "password": "password",
         "status": "active" 
    }

    Возможные значения поля «Статус»:
    * «active» — пользователь активен,
    * «blocked» — пользователь заблокирован.

    В случае успешного создания пользователя возвращается код 200.

    При повторной передаче пользователя с таким же логином будет выполнена перезапись данных пользователя.

Для активации тестового режима при запуске SUT нужно указать флаг -P:profile=test, то есть: java -jar app-ibank.jar -P:profile=test.

Важно: если вы не активируете тестовый режим, любые запросы на http://localhost:9999/api/system/users будут вам возвращать 404 Not Found.

Вам нужно самостоятельно изучить реакцию приложения на различные комбинации случаев, для этого придётся вспомнить комбинаторику:
* наличие пользователя;
* статус пользователя;
* невалидный логин;
* невалидный пароль.

Дополнительно: оцените время, которое вы затратили на автоматизацию, и время, за которое вы проверили бы те же сценарии вручную, используя для тестирования интерфейса браузер и Postman для доступа к открытому API.

Приложите к решению задачи в формате:

* время, затраченное на ручное тестирование (минут): x;
* время, затраченное на автоматизацию (минут): y.
