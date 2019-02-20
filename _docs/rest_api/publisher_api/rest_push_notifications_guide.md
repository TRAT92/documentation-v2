---
title: Работа с push-уведомлениями
permalink: rest_push_notifications_guide.html
sidebar: evorestpublisherguides
tags: []
product: Publisher API
---

{% include note.html content="API push-уведомлений описан в [справочнике](./rest_push_notifications.html)." %}

С помощью Облака Эвотор, вы можете передавать _push-уведомления_ (далее также _уведомления_) своему приложению на смарт-терминал.
В зависимости от логики приложения, установленного на смарт-терминале, уведомления позволяют решать различные задачи.
Например, вы можете оповещать пользователей или передавать команды своему приложению.

Обратите внимание, что при передаче push-уведомления вам обязательно требуется указать устройства, которые его получат. Такой подход позволяет доставлять уведомления адресно. Так, например, устройства, установленные в разных магазинах, могут получить разные уведомления о необходимых закупках, в зависимости от остатков в соответствующем магазине.

Пример cURL-команды для передачи push-уведомления в приложение, установленное на массиве устройств:

```shell
curl -X POST 'https://api.evotor.ru/api/apps/{application_id}/push-notifications'
-d '{"devices":["device-guid-1", "device-guid-2"],"payload":{"magic_field":123456,"magicString":"STR"}, "active_till": {timestamp}}'
-H 'Content-Type:application/json'
-H "Authorization: bearer {OAUTH_TOKEN}"
```
