#  Итоговый проект по автоматизации тестирования:
## Объект тестирования: [Ростелеком](https://b2c.passport.rt.ru)

### Для тестирования сайта были использованы:
- ручные и автоматизированные тесты
- разбиение на классы эквивалентности
- анализ граничных значений
- тестирование состояний и переходов

### [чек-лист/тест-кейсы/баг-репорты]
https://docs.google.com/spreadsheets/d/1bK3J5kyQn1X9wdTI1t85vGWTB2mQqI-PZDK79LvYTys/edit?usp=sharing

https://docs.google.com/spreadsheets/d/1goWcBS6sV814RUQe0DPOC3OwCu6k0zi4cqYExJgcJtY/edit?usp=sharing

https://docs.google.com/spreadsheets/d/13kOHkPASgssHAQXD7ll7rAD2vGmYciGvlq0BW03dh5c/edit?usp=sharing

### Тесты настроены на запуск через Run! 
### Страница восстановления пароля (как позитивные, так и негативные тесты) требует РУЧНОЙ ВВОД СИМВОЛОВ С КАРТИНКИ !!!

### Окружение: 
MacOS Monterey Version 12.5/ Chrome Version 108.0.5359.98 (Official Build) (arm64)   
Функция browser.find_element(locator).clear() почему-то не работает!   
Использована комбинация:   
.send_keys(Keys.COMMAND, 'a')   
.send_keys(Keys.DELETE)   
Для корректной работы в Windows среде необходима замена COMMAND на CONTROL

---------------------
### Папка tests: 
test_negative_auth_page - тестируем негативные сценарии страницы авторизации   
test_negative_reg_page - тестируем негативные сценарии страницы регистрации test_negative_new_pass_page - тестируем негативные сценарии страницы восстановления пароля   
test_positive_auth_page - тестируем позитивные сценарии страницы авторизации   
test_positive_reg_page - тестируем позитивные сценарии страницы регистрации   
test_positive_new_pass_page - тестируем позитивные сценарии страницы восстановления пароля

### Папка pages: 
Api_RegMail - GET-запросы к виртуальному почтовому ящику (1secmail.com) для получения валидного 
e-mail и кода для регистрации на сайте/восстановления пароля.   
locators - локаторы XPath и CSS на web-элементы сайта   
auth - функции-обёртки для локаторов, распределённые по классам в зависимости от тематики тестов   
base - функции для применения к локаторам явных ожиданий, получения главной страницы сайта и пути текущей страницы   
config - исходные статические данные   
settings - учетные данные, используемые в процессе теста
