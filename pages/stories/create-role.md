---
title: Создание роли
sidebar: general_sidebar
permalink: create-role.html
folder: stories
summary: "В разделе представлена последовательность шагов по созданию роли для Amazon Redshift с помощью сервиса по управлению доступом (IAM). Обозначенная роль позволяет кластеру Amazon Redshift обращаться к сервису Amazon S3 для загрузки данных."
---

1. Войдите в консоль управления **IAM** (если вышли из неё после выполнения предыдущего шага):

    [https://console.aws.amazon.com/iam](https://console.aws.amazon.com/iam)

2. В навигационной панели домашней страницы IAM перейдите в раздел **Roles** (Роли) и нажмите кнопку **Create role** (Создать роль):

    {% include image.html file="iam/role/aws_iam_step_2.jpg" alt="Создание роли в IAM" caption="" %}

3. Перейдите в группу **AWS service** и выберите **Redshift**:

    {% include image.html file="iam/role/aws_iam_step_3.jpg" alt="Настройки роли в IAM" caption="" %}

4. В разделе **Select your use case** выберите пункт **Redshift - Customizable** и нажмите кнопку **Next: Permissions** для добавления полномочий:

    {% include image.html file="iam/role/aws_iam_step_4.jpg" alt="Настройки роли в IAM" caption="" %}

5. В поле поиска укажите название политики *AmazonS3ReadOnlyAccess* (для загрузки данных из S3), отметьте чекбокс выбранной политики, оставьте настройки разрешений (Set permissions boundary) по-умолчанию и нажмите кнопку **Next: Tags**:

    {% include image.html file="iam/role/aws_iam_step_5.jpg" alt="Полномочия для загрузки данных из Amazon S3" caption="" %}

    {% include image.html file="iam/role/aws_iam_step_6.jpg" alt="Полномочия для загрузки данных из Amazon S3" caption="" %}

6. Укажите необходимое количество тегов, которые состоят из ключей и значений. Например, ключ - environment (среда) и значение - development (разработка). Нажмите кнопку **Next: Review** (или же пропустите шаг добавления тегов, сразу нажмите кнопку **Next: Review**):

    {% include note.html content="добавление тегов является необязательным действием. Однако, теги могут быть полезны во некоторых ситуациях. Например, с помощью них можно анализировать расходы денежных средств на используемые сервисы Amazon." %}

    {% include image.html file="iam/role/aws_iam_step_7.jpg" alt="Добавление тегов" caption="" %}

7. На заключительной странице создания роли **Review** (Обзор) обязательно укажите имя роли, ознакомьтесь с настройками и нажмите кнопку **Create role** (Создать роль):

    {% include image.html file="iam/role/aws_iam_step_8.jpg" alt="Проверка настроек создаваемой роли" caption="" %}

8. Роль для считывания данных из сервиса Amazon S3 создана и добавлена в список ролей в IAM:

    {% include image.html file="iam/role/aws_iam_step_9.jpg" alt="Созданная роль в перечне ролей IAM" caption="" %}

9. Перейдите в созданную роль и сохраните её код *ARN (Amazon Resource Name)*, который потребуется на шаге загрузки данных из корзины Amazon S3:

    {% include image.html file="iam/role/aws_iam_step_10.jpg" alt="Код ARN - Amazon Resource Name" caption="" %}

<br />
[Предыдущий шаг: создание пользователя](https://techwritex.ru/aws_docs/create-user.html)

<br />
[Следующий шаг: создание корзины S3](https://techwritex.ru/aws_docs/create-s3-bucket.html)

{% include links.html %}
