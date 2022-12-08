---
title: Creating S3 bucket
sidebar: general_sidebar
permalink: create-s3-bucket.html
folder: stories
summary: "This procedure describes how to create a bucket in Amazon S3 using AWS console."
---

1. Sign in to the [Amazon S3](https://console.aws.amazon.com/s3).

2. Choose **Create bucket**.

    {% include image.html file="s3/aws_s3_bucket_step_2.jpg" alt="Создание корзины Amazon S3" caption="" %}

3. In the **General configuration** section, for **Bucket name** type a name of your bucket, then select **Region**.

    {% include note.html content="The bucket name must: <br/> * be unique (as a domain name);<br/> * be between 3 and 63 characters long, <br/> * consist only of lowercase letters, numbers, dots (.), and hyphens (-); <br/> * begin and end with a letter or number; <br/> * not be formatted as an IP address (for instance, 192.168.5.4). <br/> For detailed information about naming, see [Bucket naming rules](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html)." %}

    {% include image.html file="s3/aws_s3_bucket_step_3.jpg" alt="Общие настройки корзины Amazon S3" caption="" %}

4. In the **Bucket settings for Block Public Access** section, select **Block all public access**.

    {% include image.html file="s3/aws_s3_bucket_step_4.jpg" alt="Публичный доступ заблокирован" caption="" %}

5. In the **Bucket Versioning** section, select **Disable**.

    {% include note.html content="Bucket Versioning is the optional step." %}

    {% include image.html file="s3/aws_s3_bucket_step_5.jpg" alt="Управление версиями корзины" caption="" %}

6. In the **Tags** section, add tags as key-value pairs (for instance, key - `environment` and value - `development`).

    {% include note.html content="Tagging is the optional step. However, [tags can help to manage, identify, and organize resources](https://docs.aws.amazon.com/general/latest/gr/aws_tagging.html)." %}

    {% include image.html file="s3/aws_s3_bucket_step_6.jpg" alt="Добавление тегов" caption="" %}

7. In the **Encryption** section, select **Disabled**.

    {% include note.html content="Encription is the optional step." %}

    {% include image.html file="s3/aws_s3_bucket_step_7.jpg" alt="Настройки шифрования" caption="" %}

8. Choose **Create bucket**.

    {% include image.html file="s3/aws_s3_bucket_step_8.jpg" alt="Создать корзину" caption="" %}

9. After creating your backet, choose the bucket name:

    {% include image.html file="s3/aws_s3_bucket_step_9.jpg" alt="Корзина S3 успешно создана" caption="" %}

    {% include image.html file="s3/aws_s3_bucket_step_10.jpg" alt="Корзина S3 успешно создана" caption="" %}

10. Download and unzip the file [tickitdb.zip](https://docs.aws.amazon.com/redshift/latest/gsg/samples/tickitdb.zip) with sample data.

11. Go back to the [Amazon S3 console](https://console.aws.amazon.com/s3), then move to your bucket (from step 9). Choose **Upload**:

    {% include image.html file="s3/aws_s3_bucket_step_11.jpg" alt="Загрузка файлов в корзину S3" caption="" %}

12. Select files (from the file tickitdb.zip) to upload into the bucket, then set **Object Permissions**. Choose **Next**.

    {% include image.html file="s3/aws_s3_bucket_step_12.jpg" alt="Полномочия на файлы" caption="" %}

13. Select **One Zone-IA**, then choose **Next**.

    {% include note.html content="For more information about storage classes, see [Using Amazon S3 storage classes](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-class-intro.html)." %}

    {% include image.html file="s3/aws_s3_bucket_step_13.jpg" alt="Выбор класса хранения" caption="" %}

14. Review settings and choose **Upload**.

    {% include image.html file="s3/aws_s3_bucket_step_14.jpg" alt="Загрузка файлов" caption="" %}

    {% include image.html file="s3/aws_s3_bucket_step_14_2.jpg" alt="Загрузка файлов" caption="" %}

15. In the bucket, choose **Create folder**.

    {% include image.html file="s3/aws_s3_bucket_step_15.jpg" alt="Создание папки" caption="" %}

16. Type the folder name (for instance, `tickit`). For encription settings, select **None**. Choose **Save**.

    {% include image.html file="s3/aws_s3_bucket_step_16.jpg" alt="Создание папки" caption="" %}

17. Select uploading files. Choose **Actions**, then **Move**.

    {% include image.html file="s3/aws_s3_bucket_step_17.jpg" alt="Перемещение файлов в папку" caption="" %}

18. Choose move destination (`tickit`), then **Choose**.

    {% include image.html file="s3/aws_s3_bucket_step_18.jpg" alt="Перемещение файлов в папку" caption="" %}

19. The data successfully prepared for transfer to the cluster.

<br />
[Previous tutorial: Creating IAM role](https://techwritex.ru/aws_docs_en/create-role.html)

<br />
[Next tutorial: Creating Redshift cluster](https://techwritex.ru/aws_docs_en/create-cluster.html)

{% include links.html %}
