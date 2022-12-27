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

Index: 1116 entries, 9 5G 4  6. 120 герц to 10C\
Data columns (total 36 columns):

| # | Column | Non-Null Count | Dtype |
|------|------|------|------|
| 0  | discount       | 1116 non-null | int64   |
| 1  | price          | 1116 non-null | int64   |
| 2  | discount_price | 1116 non-null | int64   |
| 3  | brand          | 1116 non-null | object |
| 4  | feedbacks      | 1116 non-null | int64   |
| 5  | rating         | 1116 non-null | int64   |
| 6  | link           | 1116 non-null | object |
| 7  | high_rating    | 1116 non-null | int64   |
| 8  | memory_size    | 1116 non-null | int64   |
| 9  | country        | 1116 non-null | object |
| 10 | weight         | 923 non-null  | float64 |
| 11 | width          | 809 non-null  | float64 |
| 12 | height         | 826 non-null  | float64 |
| 13 | thickness      | 739 non-null  | float64 |
| 14 | screen_resol   | 1025 non-null | object |
| 15 | screen_size_y  | 1065 non-null | float64 |
| 16 | screen_type    | 968 non-null  | object |
| 17 | MaxSDMemory    | 583 non-null  | float64 |
| 18 | RAM            | 1116 non-null | float64 |
| 19 | OperSystem     | 966 non-null  | object |
| 20 | SIMType        | 980 non-null  | object |
| 21 | Warranty       | 978 non-null  | float64 |
| 22 | CPUType        | 998 non-null  | object |
| 23 | CPUFreq        | 705 non-null  | object |
| 24 | CPUCores       | 1112 non-null | float64 |
| 25 | MainCameraMP   | 1116 non-null | int64   |
| 26 | FrontCameraMP  | 1116 non-null | int64   |
| 27 | SIMNumber      | 1100 non-null | float64 |
| 28 | Wireless       | 1009 non-null | object |
| 29 | CommunicStand  | 957 non-null  | object |
| 30 | SatelliteNavig | 905 non-null  | object |
| 31 | Battery        | 1116 non-null | int64   |
| 32 | InterfaceType  | 1003 non-null | object |
| 33 | resolution     | 1116 non-null | int64   |
| 34 | proportion     | 1116 non-null | float64 |
| 35 | sales_count    | 1116 non-null | int64 |

dtypes: float64(11), int64(12), object(13)\
memory usage: 322.6+ KB

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