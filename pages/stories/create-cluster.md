---
title: Creating Redshift cluster
sidebar: general_sidebar
permalink: create-cluster.html
folder: stories
summary: "This procedure describes how to create an Amazon Redshift cluster."
# simple_map: true
# map_name: usermap
# box_number: 1
---

1. Sign in to the [Amazon Redshift console](https://console.aws.amazon.com/redshift). 

2. Select **AWS region**, where you want your cluster to reside. For instance, `N. Virginia`.

    {% include image.html file="cluster/cluster_step_2_1.jpg" alt="Выбор AWS региона" caption="" %}

    <!-- {% include image.html file="cluster/cluster_step_2_2.jpg" alt="Перечень AWS регионов" caption="" %} -->

3. In the navigation pane, choose **Clusters**, then **Create cluster**.

    {% include image.html file="cluster/cluster_step_3_1.jpg" alt="Переход в раздел создания кластеров" caption="" %}

    {% include image.html file="cluster/cluster_step_3_3.jpg" alt="Кнопка создания кластера" caption="" %}

4. Enter **Cluster identifier**, then chooose **Free trial**.

    {% include note.html content="The identifier must be from 1-63 characters. Valid characters are lowercase and hyphen." %}

    {% include important.html content="When you start your trial, you will receive 750 free hours per month for two full months. If you are running multiple nodes, you may exceed 750 hours of usage in one month. To stop using trial hours, create a snapshot to restore later, and delete your cluster." %}

    {% include image.html file="cluster/cluster_step_4.jpg" alt="Конфигурация кластера" caption="" %}

5. В разделе **Database configuration** (Конфигурация базы данных) опционально укажите значения для полей *Database name* (Имя базы данных) и *Database port* (Порт базы данных), а также обязательно укажите значения для *Master user name* (Имя главного пользователя) и *Master user password* (Пароль главного пользователя):

    {% include image.html file="cluster/cluster_step_5.jpg" alt="Конфигурация базы данных" caption="" %}

6. В разделе **Cluster permissions** (Разрешения для кластера) выберите созданную IAM роль и нажмите кнопку **Add IAM role** (Добавить IAM роль):

    {% include image.html file="cluster/cluster_step_6_1.jpg" alt="Добавление роли для загрузки данных из S3" caption="" %}

    {% include image.html file="cluster/cluster_step_6_2.jpg" alt="Добавление роли для загрузки данных из S3" caption="" %}

    {% include image.html file="cluster/cluster_step_6_3.jpg" alt="Добавление роли для загрузки данных из S3" caption="" %}

7. Нажмите кнопку **Create cluster** (Создать кластер):

    {% include image.html file="cluster/cluster_step_7.jpg" alt="Создание кластера" caption="" %}

    {% include image.html file="cluster/cluster_step_7_2.jpg" alt="Создание кластера" caption="" %}

    {% include image.html file="cluster/cluster_step_7_3.jpg" alt="Создание кластера" caption="" %}


<br />
[Previous tutorial: Creating S3 bucket](https://techwritex.ru/aws_docs_en/create-s3-bucket.html)

<br />
[Next tutorial: Running queries](https://techwritex.ru/aws_docs_en/run-queries.html)

{% include links.html %}
