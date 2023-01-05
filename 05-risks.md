# Описание рисков реализации #
## Бизнес-риски ##
1. Сложность и затраты на реализацию социальных фичей может не дать той степени вовлечённости пользователей, на которую рассчитывает компания.
2. Сложность и затраты на реализацию интеграции с фитнес-функциями различных устройств может не привести к росту продаж и повышению доверия к бренду.
3. Стремление к охвату разных социальных групп, пользователей разных возрастов и разных видов спорта увеличивает время и объём разработки; необходима поэтапная реализация и тестирование.

## Технические риски ##
1. Ошибки в определении гео-локации, связанные с использованием VPN, политиками безопасности на устройствах пользователя могут привести к некорректной работе сервисов, ориентированных на поиск социальных групп и выдачу рекомендаций на основании гео-позиции пользователя.
2. Сложность интеграции с уже имеющимися сервисами: сервисы могут быть слабо документированы или вообще не иметь API, подходящие для реализации интеграции.
3. Распределённая структура сервисов и систем вызовет сложности синхронизации, разворачивания и поддержания стабильной работы сервисов.
4. Необходимость интеграции с фитнес-функциями сторонних устройств может привести к росту объёмов разработки; при попытке интегрировать "всё и сразу" возникает колоссальный объём работ, поэтому лучше предусмотреть поэтапную интеграцию с разными классами и типами устройств.
5. Необходимость реализации рекомендаций тренировок по разным видам спорта может привести к росту объёмов разработки, поэтому лучше идти по пути пилотирования рекомендаций и тренировочных программ и тестировать их применимость и востребованность на целевых группах пользователей.
6. Необходимость чёткого разделения и использования пользовательских данных приведёт к росту сложности аналитики и реализации политик информационной безопасности. Это связано с тем, что с одной стороны ПД должны быть защищены, а с другой стороны сервисам и другим пользователям должна быть видна информация о пользователе для формирования социальных групп и тренировочной статистики.