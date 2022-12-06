---
title: Создание корзины S3
sidebar: general_sidebar
permalink: create-s3-bucket.html
folder: stories
summary: "В разделе представлена последовательность шагов по созданию корзины (bucket) Amazon S3, которая будет использована в качестве источника для хранилища данных на Amazon Redshift."
---

1. Войдите в консоль управления **Amazon S3**:

    [https://console.aws.amazon.com/s3](https://console.aws.amazon.com/s3)

2. Нажмите кнопку **Create bucket** (Создать корзину):

    {% include image.html file="s3/aws_s3_bucket_step_2.jpg" alt="Создание корзины Amazon S3" caption="" %}

3. В разделе **General configuration** (Общие настройки) укажите имя корзины и регион расположения:

    {% include note.html content="требования к имени корзины: <br/> * уникальное в рамках сервиса Amazon S3 (представляйте имя корзины, как доменное имя),<br/> * минимальная длина имени 3 символа, <br/> * максимальная - 63 символа, <br/> * не содержит буквы в верхнем регистре, <br/> * состоит только из букв в нижнем регистре, цифр, точек (.) и дефисов (-), <br/> * начинается с буквы в нижнем регистре или цифры, <br/> * не имеет формат IP адреса (например, 192.168.5.4)." %}

    {% include important.html content="после того, как корзина будет создана, её имя уже не может быть изменено." %}

    {% include image.html file="s3/aws_s3_bucket_step_3.jpg" alt="Общие настройки корзины Amazon S3" caption="" %}

4. В разделе **Bucket settings for Block Public Access** (Настройки блокировки публичного доступа корзины) выберите вариант *Block all public access* (Публичный доступ к корзине и вложенным объектам полностью заблокирован):

    {% include image.html file="s3/aws_s3_bucket_step_4.jpg" alt="Публичный доступ заблокирован" caption="" %}

5. В разделе **Bucket Versioning** (Управление версиями корзины) выберите настройку для ведения версий объектов корзины. Данная настройка позволяет легко восстанавливать удаленные объекты в результате действий пользователя или же сбоев приложения. По-умолчанию версионность отключена:

    {% include image.html file="s3/aws_s3_bucket_step_5.jpg" alt="Управление версиями корзины" caption="" %}

6. Укажите необходимое количество тегов, которые состоят из ключей и значений. Например, ключ - environment (среда) и значение - development (разработка):

    {% include note.html content="добавление тегов является необязательным действием. Однако, теги могут быть полезны во некоторых ситуациях. Например, с помощью них можно анализировать расходы денежных средств на используемые сервисы Amazon." %}

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
