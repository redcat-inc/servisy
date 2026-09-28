# Event

## Карточка сервиса

<table data-header-hidden data-full-width="true"><thead><tr><th width="304"></th><th></th></tr></thead><tbody><tr><td>Название сервиса</td><td>event</td></tr><tr><td>Система</td><td><a data-mention href="../sistemy/mediaservisy.md">mediaservisy.md</a></td></tr><tr><td>Ответственная команда</td><td></td></tr><tr><td>Репозиторий</td><td><a href="https://github.com/foxford/ulms-backend/tree/main/event">https://github.com/foxford/ulms-backend/tree/main/event</a></td></tr><tr><td>Язык программирования</td><td>Rust</td></tr><tr><td>Статус</td><td> <mark style="background-color:green;">Production</mark> </td></tr></tbody></table>

## Описание

Предоставляет публичное API для всех компонентов веб-приложений и реализует хранилище событий.

_Примечание: будет полностью поглощен сервисом_ [_ULMS_](ulms-ex.-dispatcher.md)_. Сервис ULMS обеспечивает создание комнат событий в Event и проксирование запросов авторизации из Event на портал Фоксфорд._

## Схема работы

```mermaid fullWidth="false"
graph TD
  subgraph Foxford
    User((User)) --> Event

    Event

    Event .-> VerneMQ[["Verne MQ"]]
    Event --> NatsJetStream[["NATS JetStream"]]
    Event --> Redis[(Redis)]
    Event --> PostgreSQL[(PostgreSQL)]
    Event --> ModelServer["Model Server"]
  
    Event -- authz\nrequest --> ULMS
  end


```

