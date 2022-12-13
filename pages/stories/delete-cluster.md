---
title: Deleting Redshift cluster
sidebar: general_sidebar
permalink: delete-cluster.html
folder: stories
summary: "В разделе представлена последовательность шагов по сохранению слепка и удалению кластера."
---

{% include note.html content="перед удалением кластера рекомендуется сохранить слепок данных для возможного дальнейшего использования." %}

1. Войдите в консоль управления **Amazon Redshift** (если вышли из неё после выполнения предыдущего шага):

    [https://console.aws.amazon.com/redshift](https://console.aws.amazon.com/redshift)

2. В левой навигационной панели выберите **Clusters** (Кластеры) -> **Shapshots** (Снимок/слепок), нажмите кнопку **Create shapshot**:

    {% include image.html file="cluster/cluster_step_8.jpg" alt="Создать слепок данных" caption="" %}

3. Укажите параметры слепка и нажмите кнопку **Create snapshot** (Создать слепок):

    {% include image.html file="cluster/cluster_step_9.jpg" alt="Параметры слепка" caption="" %}

	{% include image.html file="cluster/cluster_step_10.jpg" alt="Перечень слепков" caption="" %}

4. С помощью левой навигационной панели перейдите в раздел **Clusters** (Кластеры) и выберите кластер, который планируете удалить.

5. В контекстном (выпадающем) меню **Actions** (Действия) выберите пункт **Delete** (Удалить):

    {% include image.html file="cluster/cluster_step_11.jpg" alt="Удаление кластера" caption="" %}

6. Подтвердите удаление. Кластер удалиться в течение нескольких секунд:

    {% include image.html file="cluster/cluster_step_12.jpg" alt="Удаление кластера" caption="" %}

    <br />
[Previous tutorial: Loading sample data](https://techwritex.ru/aws_docs_en/load-data-from-s3.html)


{% include links.html %}
