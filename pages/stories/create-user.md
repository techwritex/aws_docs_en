---
title: Создание пользователя
sidebar: general_sidebar
permalink: create-user.html
folder: stories
summary: "В разделе представлена последовательность шагов по созданию пользователя с полномочиями на чтение данных Amazon Redshift и выполению запросов с помощью встроенного редактора."
---

{% include important.html content="предполагается, что у разработчика имеется учётная запись AWS для выполнения работ по развёртыванию хранилища данных с помощью инфраструктуры AWS. Если учётная запись отсутствует, сначала необходимо пройти регистрацию по ссылке [https://portal.aws.amazon.com/billing/signup](https://portal.aws.amazon.com/billing/signup), затем вернуться к данному руководству. Также политиками безопасности AWS настоятельно рекомендуется максимально сократить или запретить использование аккаунта с правами root, созданного при регистрации. Для работы с сервисами необходимо создать отдельных пользователей и/или группы пользователей и назначить им минимальные привелегии." %}

1. Войдите в консоль управления AWS:

    [https://console.aws.amazon.com/](https://console.aws.amazon.com/)

2. В списке сервисов найдите сервис управления доступом **(IAM)** или воспользуйтесь строкой поиска, а затем перейдите на домашнюю страницу сервиса IAM:

    {% include image.html file="iam/role/aws_iam_step_1.jpg" alt="Поиск сервиса управления доступом IAM" caption="" %}

3. Перейдите в раздел **Users** (Пользователи) и выберите пользователя, которому планируете предоставить необходимые полномочия. Если пользователи отсутствуют, то создайте нового пользователя. Для этого нажмите кнопку **Add user** (Добавить пользователя):

    {% include image.html file="iam/user/aws_editor_step_1.jpg" alt="Создание пользователя" caption="" %}

4. Укажите значение поля **User name** (Имя пользователя). В настройках **Access type** (Тип доступа) выберите опцию **AWS Management Console access** (Доступ к консоли управления AWS). Создайте самостоятельно пароль или воспользуйтесь функцией автогенерации пароля. Далее нажмите кнопку перехода к разделу предоставлению полномочий **Next: Permissions**:

    {% include image.html file="iam/user/aws_editor_step_2.jpg" alt="Настройки пользовтеля" caption="" %}

5. В разделе полномочий перейдите во вкладку **Attach existing policies directly** (Добавление существующих полномочий напрямую) и в поле поиска укажите следующие имена полномочий: 
    - AmazonRedshiftQueryEditor (полномочия на редактор запросов Amazon Redshift),
    - AmazonRedshiftReadOnlyAccess (полномочия на чтение данных Amazon Redshift):

    {% include image.html file="iam/user/aws_editor_step_3.jpg" alt="Настройки пользовтеля" caption="" %}

    {% include image.html file="iam/user/aws_editor_step_4.jpg" alt="AmazonRedshiftQueryEditor" caption="" %}

    {% include image.html file="iam/user/aws_editor_step_5.jpg" alt="AmazonRedshiftReadOnlyAccess" caption="" %}

6. После выбора полномочий нажмите кнопку **Next: Tags** для перехода к разделу добавления тегов:

    {% include image.html file="iam/user/aws_editor_step_6.jpg" alt="Выбранные полномочия" caption="" %}

7. Укажите необходимое количество тегов, которые состоят из ключей и значений. Например, ключ - environment (среда) и значение - development (разработка). Нажмите кнопку **Next: Review** (или же пропустите шаг добавления тегов, сразу нажмите кнопку **Next: Review**):

    {% include note.html content="добавление тегов является необязательным действием. Однако, теги могут быть полезны во некоторых ситуациях. Например, с помощью них можно анализировать расходы денежных средств на используемые сервисы Amazon." %}

    {% include image.html file="iam/user/aws_editor_step_7.jpg" alt="Добавление тегов" caption="" %}

8. Ознакомьтесь с настройками пользователя и нажмите кнопку **Create user** (Создать пользователя):

    {% include image.html file="iam/user/aws_editor_step_8.jpg" alt="Обзор настройки пользователя" caption="" %}

9. Пользователь с необходимыми полномочиями успешно создан. Сохраните файл с информацией для доступа (Download.csv) и/или отправьте её по электронной почте:

    {% include image.html file="iam/user/aws_editor_step_9.jpg" alt="Сохранение файла с информацией для доступа" caption="" %}

<br />
[Следующий шаг: создание роли](https://techwritex.ru/aws_docs/create-role.html)

{% include links.html %}
