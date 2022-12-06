---
title: Подключение к кластеру и выполнение запросов
sidebar: general_sidebar
permalink: run-queries.html
folder: stories
summary: "В разделе представлена последовательность шагов по соединению с кластером и выполнению sql-запросов с помощью встроенного редактора."
---

{% include note.html content="встроенный редактор имеет ряд ограничений, поэтому для продуктивных данных рекомендуется использовать SQL-клиент, который поддерживает драйвера JDBC или ODBC. Тем не менее, для ознакомительных учебных целей возможностей встроенного редактора достаточно." %}

1. Войдите в консоль управления **Amazon Redshift** (если вышли из неё после выполнения предыдущего шага):

    [https://console.aws.amazon.com/redshift](https://console.aws.amazon.com/redshift)

2. В левой навигационной панели выберите пункт **Editor** (Редактор), затем **Query editor** (Редактор запросов):

    {% include image.html file="editor/editor_step_2.jpg" alt="Запуск редактора запросов" caption="" %}

3. В окне **Connect to database** (Соединение с базой данных) укажите параметры, которые были указаны при создании кластера ([п.5 шага "Создание кластера"](/create-cluster.html)) и нажмите кнопку **Connect to database** (Соединиться с базой данных):

    {% include image.html file="editor/editor_step_3.jpg" alt="Соединение с базой данных" caption="" %}

4. В открывшемся интерфейсе редактора из списка схем выберите **Public**:

    {% include image.html file="editor/editor_step_4_1.jpg" alt="Выбор схемы" caption="" %}

    {% include image.html file="editor/editor_step_4_2.jpg" alt="Выбор схемы" caption="" %}

5. В редакторе запросов введите код создания таблицы *Cars* (*Автомобили*) и нажмите кнопку **Run** (Запустить):

    ```sql
    create table cars(bodystyle varchar (10), model varchar(20));
    ````

    {% include image.html file="editor/editor_step_5_1.jpg" alt="Создание таблицы" caption="" %}

    {% include image.html file="editor/editor_step_5_2.jpg" alt="Создание таблицы" caption="" %}

6. Перед  вводом новой команды нажмите кнопку **Clear** (Очистить) для удаления предыдущего кода в поле ввода редактора.

7. Введите команду заполнения таблицы *Cars* (Автомобили) и нажмите кнопку **Run** (Запустить):

    ```sql
    insert into cars values 
    ('Sedan', 'Nissan Versa'),
    ('Sedan', 'Honda Civic'),
    ('Sedan', 'Toyota Avalon'),
    ('Coupe', 'Ford Mustang'),
    ('Coupe', 'Porsche Boxster'),
    ('Hatchback', 'Volkswagen Golf'),
    ('Hatchback', 'Audi A7'),
    ('SUV', 'Ford Expedition'),
    ('SUV', 'Chevrolet Tahoe');
    ````

    {% include image.html file="editor/editor_step_7.jpg" alt="Заполнение таблицы" caption="" %}

8. Для просмотра содержимого таблицы выполните следующий запрос:

    ```sql
    select * from cars;
    ````

    {% include image.html file="editor/editor_step_8_1.jpg" alt="Запрос данных" caption="" %}

    {% include image.html file="editor/editor_step_8_2.jpg" alt="Запрос данных" caption="" %}

9. Для выгрузки результатов в файл выберите нужный формат в меню **Export** (Экспорт):

    {% include image.html file="editor/editor_step_9.jpg" alt="Выгрузка результатов в файл" caption="" %}

10. SQL-запросы с помощью встроенного редактора успешно выполняются.

<br />
[Предыдущий шаг: создание кластера](https://techwritex.ru/aws_docs/create-cluster.html)

<br />
[Следующий шаг: загрузка данных из Amazon S3](https://techwritex.ru/aws_docs/load-data-from-s3.html)

{% include links.html %}
