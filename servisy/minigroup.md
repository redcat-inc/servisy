# Minigroup

## Карточка сервиса

<table data-header-hidden data-full-width="true"><thead><tr><th width="304"></th><th></th></tr></thead><tbody><tr><td>Название сервиса</td><td>webinar</td></tr><tr><td>Система</td><td><a data-mention href="../sistemy/mediaservisy.md">mediaservisy.md</a></td></tr><tr><td>Ответственная команда</td><td></td></tr><tr><td>Репозиторий</td><td><a href="https://github.com/foxford/ulms-application">https://github.com/foxford/ulms-application</a></td></tr><tr><td>Язык программирования</td><td>JavaScript</td></tr><tr><td>Статус</td><td> <mark style="background-color:green;">Production</mark> </td></tr></tbody></table>

## Описание

Веб-приложение реализующее мини-групповой онлайн-класс.

## Схема работы

```mermaid fullWidth="false"
graph TD
  subgraph Foxford
    User((User)) ---> Minigroup
    VerneMQ[[Verne MQ]] -- user\nnotifications --> Minigroup

    Minigroup

    Minigroup --> ULMS
    Minigroup --> Conference
    Minigroup --> Event
    Minigroup --> Storage

    Minigroup ---> Stoege
    Minigroup ---> FVS
  end

Minigroup ----> S3[(Yandex S3)]
Minigroup -----> TopMind

```

