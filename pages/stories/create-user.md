---
title: Create a user
sidebar: general_sidebar
permalink: create-user.html
folder: stories
summary: "This procedure describes how to create a user with necessary permissions."
---

{% include important.html content="According to best practice, use the root user for [tasks it's required](https://docs.aws.amazon.com/accounts/latest/reference/root-user-tasks.html); for other tasks create new IAM users and grant them least-privilege permissions to perform the tasks." %}

1. Sign in to the [AWS console](https://console.aws.amazon.com/).

2. In the AWS services list, find **IAM** (AWS Identity and Access Management) web service or enter IAM in the input field to choose the service.

    {% include image.html file="iam/role/aws_iam_step_1.jpg" alt="Поиск сервиса управления доступом IAM" caption="" %}

3. In the navigation pane, choose **Users**, then **Add user**.

    {% include image.html file="iam/user/aws_editor_step_1.jpg" alt="Создание пользователя" caption="" %}

4. On the **User details** page, for **User name** specify the user name (for instance, `mycloudsolnotes`). Select **AWS Management Console access**, then **Custom password**. Type initial password and choose **Next: Permissions**.

    {% include image.html file="iam/user/aws_editor_step_2.jpg" alt="Настройки пользовтеля" caption="" %}

5. On the **Permissions** page, choose **Attach existing policies directly** and select the following policies: 
    - **AmazonRedshiftQueryEditor**,
    - **AmazonRedshiftReadOnlyAccess**.

    {% include image.html file="iam/user/aws_editor_step_3.jpg" alt="Настройки пользовтеля" caption="" %}

    {% include image.html file="iam/user/aws_editor_step_4.jpg" alt="AmazonRedshiftQueryEditor" caption="" %}

    {% include image.html file="iam/user/aws_editor_step_5.jpg" alt="AmazonRedshiftReadOnlyAccess" caption="" %}

6. Choose **Next: Tags**.

    {% include image.html file="iam/user/aws_editor_step_6.jpg" alt="Выбранные полномочия" caption="" %}

7. On the **Tags** page, add tags as key-value pairs (for instance, key - `environment` and value - `development`). Choose **Next: Review**.

    {% include note.html content="Tagging is the optional step. However, [tags can help to track and control access for users](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_iam-tags.html)." %}

    {% include image.html file="iam/user/aws_editor_step_7.jpg" alt="Добавление тегов" caption="" %}

8. Review new user's settings and choose **Create user**.

    {% include image.html file="iam/user/aws_editor_step_8.jpg" alt="Обзор настройки пользователя" caption="" %}

9. On the **Complete** page, download user security credentials or send email with login instructions to the user. 

    {% include image.html file="iam/user/aws_editor_step_9.jpg" alt="Сохранение файла с информацией для доступа" caption="" %}

<br />
[Next tutorial: Create a role](https://techwritex.ru/aws_docs_en/create-role.html)

{% include links.html %}
