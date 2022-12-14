---
title: Running queries 
sidebar: general_sidebar
permalink: run-queries.html
folder: stories
summary: "This procedure describes how to connect to the cluster and querying it using the query editor."
---

1. Sign in to the [Amazon Redshift console](https://console.aws.amazon.com/redshift) (if you leave it after the [previous tutorial](https://techwritex.ru/aws_docs_en/create-cluster.html)):

2. In the navigation pane, choose **Editor**, then **Query editor**.

    {% include image.html file="editor/editor_step_2.jpg" alt="Запуск редактора запросов" caption="" %}

3. In the **Connect to database** section, enter the connection parameters from the step 5 of [**Creating cluster**](https://techwritex.ru/aws_docs_en/create-cluster.html) tutorial, then choose **Connect to database**.

    {% include image.html file="editor/editor_step_3.jpg" alt="Соединение с базой данных" caption="" %}

4. Choose `public` schema.

    {% include image.html file="editor/editor_step_4_1.jpg" alt="Выбор схемы" caption="" %}

    {% include image.html file="editor/editor_step_4_2.jpg" alt="Выбор схемы" caption="" %}

5. Create `Cars` table in the cluster (add the following sql, then choose **Run**).

    ```sql
    create table cars(bodystyle varchar (10), model varchar(20));
    ````

    {% include image.html file="editor/editor_step_5_1.jpg" alt="Создание таблицы" caption="" %}

    {% include image.html file="editor/editor_step_5_2.jpg" alt="Создание таблицы" caption="" %}

6. Before the next command, choose **Clear**.

7. Put some sample data into the `Cars` table using `INSERT INTO` command, then choose **Run**.

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

8. Try an example query using `SELECT` command.

    ```sql
    select * from cars;
    ````

    {% include image.html file="editor/editor_step_8_1.jpg" alt="Запрос данных" caption="" %}

    {% include image.html file="editor/editor_step_8_2.jpg" alt="Запрос данных" caption="" %}

9. Select **Export** option to save the query result.

    {% include image.html file="editor/editor_step_9.jpg" alt="Выгрузка результатов в файл" caption="" %}

<br />
[Previous tutorial: Creating Redshift cluster](https://techwritex.ru/aws_docs_en/create-cluster.html)

<br />
[Next tutorial: Loading sample data](https://techwritex.ru/aws_docs_en/load-data-from-s3.html)

{% include links.html %}
