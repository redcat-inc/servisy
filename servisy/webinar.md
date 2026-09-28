# Webinar

## Карточка сервиса

<table data-header-hidden data-full-width="true"><thead><tr><th width="304"></th><th></th></tr></thead><tbody><tr><td>Название сервиса</td><td>webinar</td></tr><tr><td>Система</td><td><a data-mention href="../sistemy/mediaservisy.md">mediaservisy.md</a></td></tr><tr><td>Ответственная команда</td><td></td></tr><tr><td>Репозиторий</td><td><a href="https://github.com/foxford/ulms-application">https://github.com/foxford/ulms-application</a></td></tr><tr><td>Язык программирования</td><td>JavaScript</td></tr><tr><td>Статус</td><td> <mark style="background-color:green;">Production</mark> </td></tr></tbody></table>

## Описание

Веб-приложение реализующее вебинарный онлайн-класс.

## Схема работы

```mermaid fullWidth="false"
graph TD
  subgraph Foxford
    User((User)) ---> Webinar
    VerneMQ[[Verne MQ]] -- user\nnotifications --> Webinar

    Webinar

    Webinar --> ULMS
    Webinar --> Conference
    Webinar --> Event
    Webinar --> Storage

    Webinar ---> Stoege
    Webinar ---> FVS
  end

Webinar ----> S3[(Yandex S3)]
Webinar -----> TopMind


```

