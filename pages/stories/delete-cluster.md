---
title: Deleting Redshift cluster
sidebar: general_sidebar
permalink: delete-cluster.html
folder: stories
summary: "This procedure describes how to create a snapshot and delete the cluster."
---

{% include note.html content="Before deleting the cluster, create a snapshot to restore the cluster latter, if you need. Be aware snapshots accrue storage charges. Delete snapshots when you no longer need them." %}

1. Sign in to the [Amazon Redshift console](https://console.aws.amazon.com/redshift) (if you leave it after the [previous tutorial](https://techwritex.ru/aws_docs_en/load-data-from-s3.html)):

2. In the navigation pane, choose **Clusters** > **Shapshots** > **Create shapshot**.

    {% include image.html file="cluster/cluster_step_8.jpg" alt="Создать слепок данных" caption="" %}

3. Select snapshot parameters, then choose **Create snapshot**.

    {% include image.html file="cluster/cluster_step_9.jpg" alt="Параметры слепка" caption="" %}

	{% include image.html file="cluster/cluster_step_10.jpg" alt="Перечень слепков" caption="" %}

4. In the navigation pane, go to **Clusters**, then check the cluster you want to delete.

5. Choose **Actions** > **Delete**.

    {% include image.html file="cluster/cluster_step_11.jpg" alt="Удаление кластера" caption="" %}

6. Confirm deleting. The cluster will be deleted within a few seconds.

    {% include image.html file="cluster/cluster_step_12.jpg" alt="Удаление кластера" caption="" %}

    <br />
[Previous tutorial: Loading sample data](https://techwritex.ru/aws_docs_en/load-data-from-s3.html)


{% include links.html %}
