# Datathon 2022 

><img align="right" width="130" height="130" src="https://user-images.githubusercontent.com/78375128/209393192-0b0016f6-a7ba-497d-a1e5-14df769c4816.png">
>
>## Команда «DataHunters»
>
>ШМЕЛЬКОВ Юрий, МАКЕЕВА Анастасия, ОЖЕРЕЛЬЕВ Виктор, АРАГОДИН Николай, ЛЮЛЯ Данила, ПОНОМАРЕВ Глеб.

# Сбор и анализ данных о товарах с Wildberries.

## Описание датасета

В датасете содержится информация о смартфонах: бренды, основные характеристики, цены, скидки, количество отзывов, ссылка в каталоге.

Основная идея для цели использования датасета - оценка влияния характеристик на спрос пользователей маркетплейса. Так же датасет может быть использован для выбора актуального ассортимента оптовыми компаниями. В дальнейшем датасет можно использовать для аналитики, обучения моделей, решения задач кластеризации.

## Структура датасета
Int64Index: 1119 entries, 0 to 1118\
Data columns (total 38 columns):

| # | Column  | Non-Null Count | Dtype  |
|------|------|------|------| 
|0  | Наименование      | 1118 non-null  | object |
|1  | Скидка            | 1119 non-null  | int64   |
|2  | Цена              | 1119 non-null  | int64   |
|3  | Цена со скидкой   | 1119 non-null  | int64   |
|4  | Бренд             | 1119 non-null  | object |
|5  | feedbacks         | 1119 non-null  | int64   |
|6  | rating            | 1119 non-null  | int64   |
|7  | Ссылка            | 1119 non-null  | object |
|8  | high_rating       | 1119 non-null  | int64   |
|9  | memory_size       | 904 non-null   | object |
|10 | country           | 1038 non-null  | object |
|11 | weight            | 881 non-null   | object |
|12 | width             | 811 non-null   | object |
|13 | height            | 828 non-null   | object |
|14 | thickness         | 741 non-null   | object |
|15 | screen_resol      | 1026 non-null  | object |
|16 | screen_size       | 1058 non-null  | object |
|17 | screen_type       | 971 non-null   | object |
|18 | MaxSDMemory       | 584 non-null   | object |
|19 | PhoneMemory       | 1081 non-null  | object |
|20 | RAM               | 1032 non-null  | object |
|21 | OperSystem        | 949 non-null   | object |
|22 | SIMType           | 983 non-null   | object |
|23 | Warranty          | 992 non-null   | object |
|24 | CPUType           | 999 non-null   | object |
|25 | CPUFreq           | 708 non-null   | object |
|26 | CPUCores          | 1020 non-null  | object |
|27 | MainCameraMP      | 609 non-null   | object |
|28 | FrontCameraMP     | 472 non-null   | object |
|29 | SIMNumber         | 1043 non-null  | object |
|30 | Wireless          | 1012 non-null  | object |
|31 | CommunicStand     | 960 non-null   | object |
|32 | SatelliteNavig    | 908 non-null   | object |
|33 | Battery           | 1002 non-null  | object |
|34 | InterfaceType     | 1006 non-null  | object |
|35 | MusicWorkingTime  | 0 non-null     | float64 |
|36 | VideoWorkingTime  | 0 non-null     | float64 |
|37 | sales_count       | 1119 non-null  | int64   |
dtypes: float64(2), int64(7), object(29)\
memory usage: 340.9+ KB

## Методы сбора и обработки данных
Для сбора данных переиспользован и адаптирован под задачу команды python модуль для парсинга торговой площадки Wildberries, основанный на работе с API сайта, используя библиотеки requests, json, pandas.
Данные, в виде каталога Wildberries, получены в json формате по url = 'https://www.wildberries.ru/webapi/menu/main-menu-ru-ru.json' и сохранены в файл.

## Источники
Данные с сайта https://www.wildberries.ru/\
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
    │   ├── Смартфоны_from_1000_to_200000.csv
    │   ├── ProcessedDatasetMemory.csv
    │   └── ProcessedDataset.csv
    ├── DataAnalysisVisu.ipynb           # ноутбук с визуализацией
    ├── DataProcessing.ipynb             # ноутбук с обработкой данных - часть 1
    ├── DataProcessing_2.ipynb           # ноутбук с обработкой данных - часть 2
    ├──Dataton_parser1.ipynb             # ноутбук с парсером данных - часть 1
    ├──Dataton_parser2.ipynb             # ноутбук с парсером данных - часть 2
    ├──Dataset_final.csv                 # финальный датасет
    └── README.md