# Editor

## Карточка сервиса

<table data-header-hidden data-full-width="true"><thead><tr><th width="304"></th><th></th></tr></thead><tbody><tr><td>Название сервиса</td><td>editor</td></tr><tr><td>Система</td><td><a data-mention href="../sistemy/mediaservisy.md">mediaservisy.md</a></td></tr><tr><td>Ответственная команда</td><td></td></tr><tr><td>Репозиторий</td><td><a href="https://github.com/foxford/ulms-media-editor">https://github.com/foxford/ulms-media-editor</a></td></tr><tr><td>Язык программирования</td><td>JavaScript</td></tr><tr><td>Статус</td><td> <mark style="background-color:green;">Production</mark> </td></tr></tbody></table>

## Описание

Веб-приложение для редактирования видео записи и событий онлайн-класса.

## Схема работы

```mermaid fullWidth="false"
graph TD
  subgraph Foxford
    User((Admin)) ---> Editor

    Editor

    Editor --> ULMS
    Editor --> Event
    Editor --> Storage

    Editor ---> Stoege
  end

Editor ----> S3[(Yandex S3)]
```

