---
title: Running queries 
sidebar: general_sidebar
permalink: run-queries.html
folder: stories
summary: "This procedure describes how to connect the cluster and querying it using the query editor."
---

1. Sign in to the [Amazon Redshift console](https://console.aws.amazon.com/redshift)(if you leave it after the previous step):

2. In the navigation pane, choose **Editor**, then **Query editor**.

    {% include image.html file="editor/editor_step_2.jpg" alt="Запуск редактора запросов" caption="" %}

3. In the **Connect to database** section, specify parameters from the [**Creating cluster**](/create-cluster.html) step, then choose **Connect to database**.

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
