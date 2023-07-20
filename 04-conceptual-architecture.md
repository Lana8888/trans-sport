# Концептуальная архитектура #

![Концептуальная архитектура приложений/ сервисов](Conceptual-Arch-3.png)
## Сервисы и компоненты ##
1. <b>Buying Service (1-N)</b> - существующие сервисы/ приложения для покупок.
2. <b>Sport Service (1-M)</b> - существующие сервисы/ приложения для различных видов спорта.
3. <b>Clients Service</b> - сервис управления клиентскими данными (регистрация пользователя, авторизация, хранение данных о пользователях). Нуждается в доработке с целью добавления новых полей в БД клиентов, которые позволят идентифицировать виды спорта, снаряжение пользователя, его предпочтения и персональные настройки приватности.
4. <b>Products Service</b> - существующий сервис продуктов компании (допущение - такой сервис уже есть, и туда собираются данные обо всех продуктах).
5. <b>Social Networks</b> - внешние приложения соц. сетей, с которыми (возможно) потребуется интеграция.
6. <b>Fitness Sensor Plugin</b> - плагин/ сервис для интеграции с фитнес-функциями смартфона, датчиками пульса/ сердцебиения/ насыщения кислородом/ etc., фитнес-браслетом. Возможно, потребуются отдельные сервисы для каждого вида внешних датчиков/ приложений. 
7. <b>Smartphone</b> - фитнес-функции смартфона пользователя.
8. <b>Sensor</b> - датчики пульса/ сердцебиения/ насыщения кислородом/ etc.
9. <b>Fitness Band</b> - фитнес-браслеты пользователя. Возможно, потребуется разработка интегратора для основных производителей фитнес-браслетов.
10. <b>Statistics Service</b> - сервис для сбора и обработки статистики (тренировки, метрики пользователя, победы, награды, достижение тренировочных целей). 
11. <b>Training Service</b> - сервис для составления тренировок, выдачи рекомендаций по тренировкам, учёта пользовательского инвентаря.
12. <b>Social Service</b> - сервис для управления социальными группами (создание групп по интересам, поиск пользователей по схожим интересам, добавление друзей).
13. <b>Social Network Plugin</b> - плагины для подключения к соц. сетям (возможно, будут нужны, а возможно и нет).
14. <b>Geo Service</b> - сервис определения гео-локации, связь пользователей с гео-параметрами.
15. <b>Target Service</b> - сервис для таргетирования рекомендаций (новости, покупки) и промо-акций.
16. <b>User Front (Browser, Mobile)</b> - пользовательский фронт-сервис для выдачи контента, поставляемого другими сервисами. Возможно, нужна разработка web-версии и мобильной версии приложения.

## Интеграции ##
### Внешние интеграции (с существующими приложениями/ сервисами) ###
1. <b>Target Service - Buying Service (1-N)</b>: интеграция таргета с сервисами/ приложениями для покупок (получение промоакций, скидок).
2. <b>Social Network Plugin - Social Networks</b>: интеграция с соц. сетями для (возможного) использования их при формировании групп пользователей.
3. <b>Training Service - Sport Service (1-M)</b>: интеграция с сервисами/ приложениями для различных видов спорта (получение информации о составлении тренировок, особенностях разных видов спорта).
4. <b>Target Service - Products Service</b>: интеграция таргета с сервисом продуктов (получение информации о продуктах).
5. <b>Geo Service - Clients Service</b>: интеграция с клиентским сервисом (получение информации о клиентах, привязка клиента к гео-локации).
6. <b>Social Service - Clients Service</b>: интеграция с клиентским сервисом (получение информации о клиентах, передача информации о вхождении клиента в группы).
7. <b>Statistics Service - Clients Service</b>: интеграция с клиентским сервисом (получение информации о клиентах, передача информации о накопленных баллах и бонусах за тренировки и победу в соревнованиях).
8. <b>Fitness Sensor Plugin - Smartphone/ Sensor/ Fitness Band</b>: интеграция с фитнес-функциями смартфона, датчиков и фитнес-браслетов (получение информации о метриках пользователя и метриках тренировки).

<i>Допущение: считаем, что Buying Service (1-N) и Products Service уже интегрированы между собою и в текущем контексте эту интеграцию не рассматриваем и не изменяем.</i>

### Интеграции на приложение фронта ###
1. <b>Buying Service (1-N) - User Front (Browser, Mobile)</b>: возможность вызова приложения для покупок с фронта, получение информации из пользовательских форм фронта (поиск, параметры товара и т.п.).
2. <b>Sport Service (1-M) - User Front (Browser, Mobile)</b>: возможность вызова приложений для различных видов спорта с фронта, получение информации из пользовательских форм фронта (поиск по виду спорта).
3. <b>Target Service - User Front (Browser, Mobile)</b>: передача таргета (рекомендации, промо, новости) на фронт.
4. <b>Geo Service - User Front (Browser, Mobile)</b>: передача гео-информации на фронт, получение параметров от пользовательских устройств/ браузеров для определения гео-локации.
5. <b>Social Network Plugin - User Front (Browser, Mobile)</b>: возможность перехода с фронта в соц. сети.
6. <b>Social Service - User Front (Browser, Mobile)</b>: передача информации на фронт о социальных группах, сбор информации с форм фронта для включения пользователя в группы, поиска друзей, участия в соревнованиях.
7. <b>Training Service - User Front (Browser, Mobile)</b>: передача на фронт информации о тренировках (рекомендации, тренировочные планы), получение с фронта информации для составления тренировки (параметры, задаваемые пользователем).
8. <b>Statistics Service - User Front (Browser, Mobile)</b>: раздача статистики на фронт.
9. <b>Clients Service - User Front (Browser, Mobile)</b>: раздача на фронт информации о пользователях (с учётом настроек приватности и политик защиты ПД), получение информации с форм фронта для регистрации, входа пользователя (авторизации, аутентификации).
10. <b>Products Service - User Front (Browser, Mobile)</b>: передача на фронт информации о продуктах, получение информации из пользовательских форм фронта (поиск, параметры продукта и т.п.).

### Внутренние интеграции (между сервисами) ###
1. <b>Training Service - Target Service</b>: передача информации о тренировках, инвентаре для формирования рекомендаций покупок пользователю.
2. <b>Geo Service - Social Service</b>: передача гео-информации для поиска социальных групп.
3. <b>Training Service - Statistics Service</b>: передача статистики для формирования рекомендаций по программе тренировок.
4. <b>Geo Service - Target Service</b>: передача гео-информации для формирования региональных промо-акций.
5. <b>Geo Service - Statistics Service</b>: передача гео-информации для формирования таблиц статистики, привязанных к гео-локации.
6. <b>Fitness Sensor Plugin - Statistics Service</b>: передача информации с фитнес-функций смартфона, датчиков, фитнес-браслетов для учёта статистики тренировок.