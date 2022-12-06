---
title: Загрузка данных из Amazon S3
sidebar: general_sidebar
permalink: load-data-from-s3.html
folder: stories
summary: "В разделе представлена последовательность шагов по загрузке данных корзины Amazon S3."
---

1. Выполните пункты 1-5 шага ["Подключение к кластеру и выполнение запросов"](/run-queries.html) (если вышли из панели управления Amazon Redshift после выполнения предыдущего шага):

2. Создайте талицы базы данных согласно файлам загруженным в корзину Amazon S3. В редакторе запросов поочередно введите представленные ниже образцы кода и нажмите кнопку **Run** (Запустить):

    ```sql
    create table users(
	userid integer not null distkey sortkey,
	username char(8),
	firstname varchar(30),
	lastname varchar(30),
	city varchar(30),
	state char(2),
	email varchar(100),
	phone char(14),
	likesports boolean,
	liketheatre boolean,
	likeconcerts boolean,
	likejazz boolean,
	likeclassical boolean,
	likeopera boolean,
	likerock boolean,
	likevegas boolean,
	likebroadway boolean,
	likemusicals boolean);   
    ````

    ```sql
    create table venue(
	venueid smallint not null distkey sortkey,
	venuename varchar(100),
	venuecity varchar(30),
	venuestate char(2),
	venueseats integer);
    ````

    ```sql
    create table category(
	catid smallint not null distkey sortkey,
	catgroup varchar(10),
	catname varchar(10),
	catdesc varchar(50));
    ````

    ```sql
    create table date(
	dateid smallint not null distkey sortkey,
	caldate date not null,
	day character(3) not null,
	week smallint not null,
	month character(5) not null,
	qtr character(5) not null,
	year smallint not null,
	holiday boolean default('N'));
    ````

    ```sql
    create table event(
	eventid integer not null distkey,
	venueid smallint not null,
	catid smallint not null,
	dateid smallint not null sortkey,
	eventname varchar(200),
	starttime timestamp);
    ````

    ```sql
    create table listing(
	listid integer not null distkey,
	sellerid integer not null,
	eventid integer not null,
	dateid smallint not null  sortkey,
	numtickets smallint not null,
	priceperticket decimal(8,2),
	totalprice decimal(8,2),
	listtime timestamp);
    ````

    ```sql
    create table sales(
	salesid integer not null,
	listid integer not null distkey,
	sellerid integer not null,
	buyerid integer not null,
	eventid integer not null,
	dateid smallint not null sortkey,
	qtysold smallint not null,
	pricepaid decimal(8,2),
	commission decimal(8,2),
	saletime timestamp);
    ````

3. Загрузите поочередно тестовые данные из корзины Amazon S3 с помощью команды **COPY** по указанному шаблону:

    ```sql
    copy users from 's3://<bucketName>/<folderName>/<fileName>' 
    credentials 'aws_iam_role=<iam-role-arn>' 
    delimiter '|' region '<aws-region>';
    ````

    где:

    - \<bucketName\> - имя корзины S3,

    - \<folderName\> - имя папки (если создавалась),

    - \<fileName\> - имя загружаемого файла,

    - \<iam-role-arn\> - код ARN роли (п.9 шаг ["Создание роли"](/create-role.html)),

    - \<aws-region\> - регион, в котором создана корзина.

    ```sql
    copy users from 's3://my-cloud-solutions-notes-bucket/tickit/allusers_pipe.txt' 
    credentials 'aws_iam_role=arn:aws:iam::779852353305:role/myFirstRedshiftRole' 
    delimiter '|' region 'us-east-1';
    ````

    {% include image.html file="editor/editor_step_10.jpg" alt="Загрузка файла из S3" caption="" %}

4. Выполните запрос загруженных данных с помощью комманды **SELECT**:

    ```sql
    SELECT firstname, lastname, total_quantity 
    FROM   (SELECT buyerid, sum(qtysold) total_quantity
        FROM  sales
        GROUP BY buyerid
        ORDER BY total_quantity desc limit 10) Q, users
    WHERE Q.buyerid = userid
    ORDER BY Q.total_quantity desc;
    ````

    {% include image.html file="editor/editor_step_11.jpg" alt="Запрос загруженных данных" caption="" %}

{% include important.html content="после выполнения всех шагов по развёртыванию хранилища данных в учебных и ознакомительных целях, настоятельно рекомендуется удалить кластер (предварительно сделать слепок данных!) во избежании начисления оплаты по окончании пробного периода." %}

<br />
[Предыдущий шаг: подключение к кластеру и выполнение запросов](https://techwritex.ru/aws_docs/run-queries.html)

<br />
[Следующий шаг: удаление кластера](https://techwritex.ru/aws_docs/delete-cluster.html)

{% include links.html %}
