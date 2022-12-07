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

4. In the **Bucket settings for Block Public Access** section select **Block all public access**.

    {% include image.html file="s3/aws_s3_bucket_step_4.jpg" alt="Публичный доступ заблокирован" caption="" %}

5. In the **Bucket Versioning** section select **Disable**:

    {% include image.html file="s3/aws_s3_bucket_step_5.jpg" alt="Управление версиями корзины" caption="" %}

6. In the **Tags** section, add tags as key-value pairs (for instance, key - `environment` and value - `development`). Choose **Next: Review**.

    {% include note.html content="Tagging is the optional step. However, [tags can help to manage, identify, and organize resources](https://docs.aws.amazon.com/general/latest/gr/aws_tagging.html)." %}

    {% include image.html file="s3/aws_s3_bucket_step_6.jpg" alt="Добавление тегов" caption="" %}

7. В разделе **Default encryption** (Шифрование) выберите значение *Disabled* (шифрование всех объектов корзины отключено):

    {% include image.html file="s3/aws_s3_bucket_step_7.jpg" alt="Настройки шифрования" caption="" %}

8. Нажмите кнопку **Create bucket** (Создать корзину):

    {% include image.html file="s3/aws_s3_bucket_step_8.jpg" alt="Создать корзину" caption="" %}

9. Корзина успешно создана. Нажмите на ссылку в виде имени корзины для перехода в неё:

    {% include image.html file="s3/aws_s3_bucket_step_9.jpg" alt="Корзина S3 успешно создана" caption="" %}

    {% include image.html file="s3/aws_s3_bucket_step_10.jpg" alt="Корзина S3 успешно создана" caption="" %}

10. Скачайте и распакуйте архив с файлами, подготовленными Amazon Web Services, по ссылке:

    [https://docs.aws.amazon.com/redshift/latest/gsg/samples/tickitdb.zip](https://docs.aws.amazon.com/redshift/latest/gsg/samples/tickitdb.zip)

11. Вернитесь в консоль Amazon S3, перейдите в созданную ранее корзину и нажмите кнопку **Upload** (Загрузить):

    {% include image.html file="s3/aws_s3_bucket_step_11.jpg" alt="Загрузка файлов в корзину S3" caption="" %}

12. Выберите файлы, укажите полномочия *Read/Write* (Чтение/Запись) на загружаемые файлы и нажмите кнопку **Next** (Далее):

    {% include image.html file="s3/aws_s3_bucket_step_12.jpg" alt="Полномочия на файлы" caption="" %}

13. Выберите класс хранения *One Zone-IA* (так как доступ к данным будет осуществляется относительно редко, но при этом должен обеспечиваться быстро) и нажмите кнопку **Next** (Далее):

    {% include image.html file="s3/aws_s3_bucket_step_13.jpg" alt="Выбор класса хранения" caption="" %}

14. Проверьте выполненные настройки и нажмите кнопку **Upload** (Загрузить):

    {% include image.html file="s3/aws_s3_bucket_step_14.jpg" alt="Загрузка файлов" caption="" %}

    {% include image.html file="s3/aws_s3_bucket_step_14_2.jpg" alt="Загрузка файлов" caption="" %}

15. В корзине создайте папку, в которую переместите загруженные файлы. Нажмите кнопку **Create folder** (Создать папку):

    {% include image.html file="s3/aws_s3_bucket_step_15.jpg" alt="Создание папки" caption="" %}

16. Укажите имя папки *tickit*, тип шифрования оставьте по-умолчанию и нажмите кнопку **Save** (Сохранить):

    {% include image.html file="s3/aws_s3_bucket_step_16.jpg" alt="Создание папки" caption="" %}

17. Отметьте загруженные файлы. В контекстном (выпадающем) меню **Actions** (Действия) выберите пункт **Move** (Переместить):

    {% include image.html file="s3/aws_s3_bucket_step_17.jpg" alt="Перемещение файлов в папку" caption="" %}

18. Укажите путь перемещения файлов и нажмите кнопку **Choose** (Выбрать):

    {% include image.html file="s3/aws_s3_bucket_step_18.jpg" alt="Перемещение файлов в папку" caption="" %}

19. Данные в корзине Amazon S3 для дальнейшей передачи их в Amazon Redshift успешно подготовлены.


<br />
[Предыдущий шаг: создание роли](https://techwritex.ru/aws_docs/create-role.html)

<br />
[Следующий шаг: создание кластера](https://techwritex.ru/aws_docs/create-cluster.html)

{% include links.html %}
