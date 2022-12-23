# Datathon 2022 
## Сбор и анализ данных о товарах с Wildberries.

#### ***Основная идея:*** собрать датасет по характеристикам смартфонов с целью оценить влияние характеристик на оценку смартфона пользователями маркетплейса. Полученный датасет может использоваться для дальнейшей аналитики, обучения различных моделей, решения задач кластеризации.
---

На первом этапе подготовлен парсер, который основан на работе и взаимодействии с API сайта Wildberries, что увеличивает скорость сбора интересующих вас данных. Данные, в виде каталога Wildberries, получены в json формате по url = 'https://www.wildberries.ru/webapi/menu/main-menu-ru-ru.json' и сохранены в файл. 
