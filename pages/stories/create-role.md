---
title: Creating IAM role
sidebar: general_sidebar
permalink: create-role.html
folder: stories
summary: "This procedure describes how to create IAM role to allow an Amazon Redshift cluster to communicate with Amazon S3."
---

1. Sign in to the [IAM console](https://console.aws.amazon.com/iam/home).

2. In the navigation pane, choose **Roles**, then **Create role**.

    {% include image.html file="iam/role/aws_iam_step_2.jpg" alt="Создание роли в IAM" caption="" %}

3. Choose **AWS service**, then **Redshift**.

    {% include image.html file="iam/role/aws_iam_step_3.jpg" alt="Настройки роли в IAM" caption="" %}

4. In the **Use case** section, select **Redshift - Customizable**, then choose **Next: Permissions**.

    {% include image.html file="iam/role/aws_iam_step_4.jpg" alt="Настройки роли в IAM" caption="" %}

5. On the **Permissions** page, select checbox **AmazonS3ReadOnlyAccess**. In the **Set permissions boundary** section, select **Create role without a permission boundary**. Choose **Next: Tags**.

    {% include image.html file="iam/role/aws_iam_step_5.jpg" alt="Полномочия для загрузки данных из Amazon S3" caption="" %}

    {% include image.html file="iam/role/aws_iam_step_6.jpg" alt="Полномочия для загрузки данных из Amazon S3" caption="" %}

6. On the **Tags** page, add tags as key-value pairs (for instance, key - `environment` and value - `development`). Choose **Next: Review**.

    {% include note.html content="Tagging is the optional step. However, [tags can help to track and control access for users](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_iam-tags.html)." %}

    {% include image.html file="iam/role/aws_iam_step_7.jpg" alt="Добавление тегов" caption="" %}

7. Review new role's settings. For **Role name** specify the role name (for instance, `myFirstRedshiftRole`). Choose **Create role**.

    {% include image.html file="iam/role/aws_iam_step_8.jpg" alt="Проверка настроек создаваемой роли" caption="" %}

8. The role has been created and added to your IAM roles.

    {% include image.html file="iam/role/aws_iam_step_9.jpg" alt="Созданная роль в перечне ролей IAM" caption="" %}

9. Choose the new role, then copy and save **Role ARN** (needed in the next tutorial).

    {% include image.html file="iam/role/aws_iam_step_10.jpg" alt="Код ARN - Amazon Resource Name" caption="" %}

<br />
[Previous tutorial: Creating IAM user](https://techwritex.ru/aws_docs_en/create-user.html)

<br />
[Next tutorial: Creating S3 bucket](https://techwritex.ru/aws_docs_en/create-s3-bucket.html)

{% include links.html %}
