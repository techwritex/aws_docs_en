---
title: Создание кластера
sidebar: general_sidebar
permalink: create-cluster.html
folder: stories
summary: "В разделе представлена последовательность шагов по созданию и настройке кластера Amazon Redshift."
# simple_map: true
# map_name: usermap
# box_number: 1
---

1. Откройте консоль **Amazon Redshift** по следующей ссылке:

    [https://console.aws.amazon.com/redshift](https://console.aws.amazon.com/redshift)

2. В правом верхнем углу консоли выберите **AWS регион**, в котором планируется создание кластера:

    {% include image.html file="cluster/cluster_step_2_1.jpg" alt="Выбор AWS региона" caption="" %}

    <!-- {% include image.html file="cluster/cluster_step_2_2.jpg" alt="Перечень AWS регионов" caption="" %} -->

3. В левой навигационной панели выберите пукт меню **Clusters** (Кластеры), после чего нажмите кнопку **Create cluster** (Создать кластер):

    {% include image.html file="cluster/cluster_step_3_1.jpg" alt="Переход в раздел создания кластеров" caption="" %}

    {% include image.html file="cluster/cluster_step_3_3.jpg" alt="Кнопка создания кластера" caption="" %}

4. Укажите значение поля **Cluster identifier** (Идентификатор кластера) и выберите конфигурацию **Free trial** (Бесплатная пробная версия):

    {% include important.html content="Конфигурация 'Free trial' предоставляет возможность работы с кластером Amazon Redshift в течение двух месяцев бесплатно (750 часов на один узел в месяц на протяжении двух месяцев). Если кластер имеет несколько узлов, бесплатный пробный период истечёт раньше двух месяцев. По истечению предоставленного времени (если преследуются обучающие цели) необходимо снять слепок с кластера (для дальнейших продуктивных действий, если потребуется) и удалить кластер. Несвоевременное удаление приведёт к начислению оплаты за использование Amazon Redshift." %}

    {% include note.html content="идентификатор кластера должен быть уникальным и состоять из следующих символов:<br />
        * строчные буквы английского алфавита (a - z),<br />
        * дефис (-).<br />
    Длина идентификатора должна составлять от 1 до 63 символов." %}

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
[Предыдущий шаг: создание корзны S3](https://techwritex.ru/aws_docs/create-s3-bucket.html)

<br />
[Следующий шаг: подключение к кластеру и выполнение запросов](https://techwritex.ru/aws_docs/run-queries.html)

{% include links.html %}
