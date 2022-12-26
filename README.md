# Datathon 2022 

><img align="right" width="110" height="110" src="https://user-images.githubusercontent.com/78375128/209393192-0b0016f6-a7ba-497d-a1e5-14df769c4816.png">
>
>## Команда «DataHunters»
>
>ШМЕЛЬКОВ Юрий, МАКЕЕВА Анастасия, ОЖЕРЕЛЬЕВ Виктор, АРАГОДИН Николай, ЛЮЛЯ Данила, ПОНОМАРЕВ Глеб.

# Сбор и анализ данных о товарах с Wildberries.

## Описание датасета

В датасете содержится информация о смартфонах: бренды, основные характеристики, цены, скидки, количество отзывов, ссылка в каталоге.

Основная идея для цели использования датасета - оценка влияния характеристик на спрос пользователей маркетплейса. Так же датасет может быть использован для выбора актуального ассортимента оптовыми компаниями. В дальнейшем датасет можно использовать для аналитики, обучения моделей, решения задач кластеризации.

## Структура датасета

RangeIndex: 1119 entries, 0 to 1118\
Data columns (total 37 columns):

| # | Column | Non-Null Count | Dtype |
|------|------|------|------|
| 0  | name           | 1116 non-null | object
| 1  | discount       | 1119 non-null | int64  |
| 2  | price          | 1119 non-null | int64  |
| 3  | discount_price | 1119 non-null | int64  |
| 4  | brand          | 1119 non-null | object
| 5  | feedbacks      | 1119 non-null | int64  |
| 6  | rating         | 1119 non-null | int64  |
| 7  | link           | 1119 non-null | object
| 8  | high_rating    | 1119 non-null | int64  |
| 9  | memory_size    | 1119 non-null | int64  |
| 10 | country        | 1119 non-null | object
| 11 | weight         | 925 non-null  | float64|
| 12 | width          | 811 non-null  | float64|
| 13 | height         | 828 non-null  | float64|
| 14 | thickness      | 741 non-null  | float64|
| 15 | screen_resol   | 1028 non-null | object
| 16 | screen_size_y  | 1068 non-null | float64|
| 17 | screen_type    | 971 non-null  | object
| 18 | MaxSDMemory    | 584 non-null  | float64|
| 19 | RAM            | 1119 non-null | float64|
| 20 | OperSystem     | 968 non-null  | object
| 21 | SIMType        | 983 non-null  | object
| 22 | Warranty       | 980 non-null  | float64|
| 23 | CPUType        | 1001 non-null | object
| 24 | CPUFreq        | 708 non-null  | object
| 25 | CPUCores       | 1115 non-null | float64|
| 26 | MainCameraMP   | 1119 non-null | int64  |
| 27 | FrontCameraMP  | 1119 non-null | int64  |
| 28 | SIMNumber      | 1103 non-null | float64|
| 29 | Wireless       | 1012 non-null | object
| 30 | CommunicStand  | 960 non-null  | object
| 31 | SatelliteNavig | 908 non-null  | object
| 32 | Battery        | 1119 non-null | int64  |
| 33 | InterfaceType  | 1006 non-null | object
| 34 | resolution     | 1119 non-null | int64  |
| 35 | proportion     | 1119 non-null | float64|
| 36 | sales_count    | 1119 non-null | int64 |

dtypes: float64(11), int64(12), object(14)\
memory usage: 332.2+ KB

## Методы сбора и обработки данных
Для сбора данных переиспользован и адаптирован под задачу команды python модуль для парсинга торговой площадки Wildberries, основанный на работе с API сайта, используя библиотеки requests, json, pandas.
Данные, в виде каталога Wildberries, получены в json формате по url = 'https://www.wildberries.ru/webapi/menu/main-menu-ru-ru.json' и сохранены в файл.

## Источники
Данные с сайта https://www.wildberries.ru \
Данные из статьи https://vk.com/@happython-parser-wildberries

## Описание ноутбуков

Ноутбуки разделены на три части: сбор данных, чистка и визуализация.

1. Два ноутбука-парсера с поэтапным сбором данных.
2. Два ноутбука-обработчика с поэтапной аналитикой и чисткой.
3. Ноутбук с визуализацией анализа на графиках.

Работа велась с помощью среды Jupyter Notebook.

## Структура репозитория

    ├── data                             # промежуточные датасеты
    │   ├── AdditionalCharacteristics.csv
    │   ├── Dataset_final.csv
    │   ├── Dataset_final_V2.csv
    │   ├── Смартфоны_from_1000_to_200000.csv
    │   ├── ProcessedDatasetMemory.csv
    │   └── ProcessedDataset.csv
    ├── DataAnalysisVisu.ipynb           # ноутбук с визуализацией
    ├── DataProcessing.ipynb             # ноутбук с обработкой данных - часть 1
    ├── DataProcessing_2.ipynb           # ноутбук с обработкой данных - часть 2
    ├── Dataton_parser1.ipynb            # ноутбук с парсером данных - часть 1
    ├── Dataton_parser2.ipynb            # ноутбук с парсером данных - часть 2
    ├── Dataset_final_V4.csv             # финальный датасет
    └── README.md