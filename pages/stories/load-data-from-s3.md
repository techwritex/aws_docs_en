---
title: Loading sample data from S3
sidebar: general_sidebar
permalink: load-data-from-s3.html
folder: stories
summary: "This procedure describes how to load data to the cluster from Amazon S3 bucket."
---

1. Repeat steps 1-5 from the [previous tutorial](https://techwritex.ru/aws_docs_en/run-queries.html) (if you leave **Amazon Redshift console**).

2. According to files in the [you S3 bucket](https://techwritex.ru/aws_docs_en/create-s3-bucket.html), create tables in the cluster. Add the following sql, then choose **Run**.

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

3. Load sample data from Amazon S3 into new tables in the cluster by using the `COPY` command.

    ```sql
    copy users from 's3://<bucketName>/<folderName>/<fileName>' 
    credentials 'aws_iam_role=<iam-role-arn>' 
    delimiter '|' region '<aws-region>';
    ````
    {% include note.html content="See `<iam-role-arn\>` in the step 9 of [Creating IAM role tutorial](https://techwritex.ru/aws_docs_en/create-role.html))." %}

    ```sql
    copy users from 's3://my-cloud-solutions-notes-bucket/tickit/allusers_pipe.txt' 
    credentials 'aws_iam_role=arn:aws:iam::779852353305:role/myFirstRedshiftRole' 
    delimiter '|' region 'us-east-1';
    ````

    {% include image.html file="editor/editor_step_10.jpg" alt="Загрузка файла из S3" caption="" %}

4. Run queries by using `SELECT` command:

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

{% include important.html content="After you have completed tutorials about Data Warehousing on AWS infrustructure, AWS recommends to delete your sample cluster. However, before deleting the clister, make a snapshot of your cluster data (to restore data latter, if you need)." %}

<br />
[Previous tutorial: Running queries](https://techwritex.ru/aws_docs_en/run-queries.html)

<br />
[Next tutorial: Deleting Redshift cluster](https://techwritex.ru/aws_docs_en/delete-cluster.html)

{% include links.html %}
