# HTTP Gateway

## Карточка сервиса

<table data-header-hidden data-full-width="true"><thead><tr><th width="304"></th><th></th></tr></thead><tbody><tr><td>Название сервиса</td><td>http-gateway</td></tr><tr><td>Система</td><td><a data-mention href="../sistemy/mediaservisy.md">mediaservisy.md</a></td></tr><tr><td>Ответственная команда</td><td></td></tr><tr><td>Репозиторий</td><td><a href="https://github.com/foxford/ulms-backend/tree/main/http-gateway">https://github.com/foxford/ulms-backend/tree/main/http-gateway</a></td></tr><tr><td>Язык программирования</td><td>Rust</td></tr><tr><td>Статус</td><td> <mark style="background-color:green;">Production</mark> </td></tr></tbody></table>

## Описание

Единственная задача сервиса это доставка системных нотификаций на HTTP колбэк портала Фоксфорд.

## Схема работы

```mermaid fullWidth="false"
graph TD
  subgraph Foxford
    VerneMQ[["Verne MQ"]] -- system\nnotifications --> HttpGateway
    HttpGateway["Http Gateway"]
    HttpGateway -- system\nnotifications --> Stoege
  end


```

