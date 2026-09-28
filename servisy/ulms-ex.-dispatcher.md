# ULMS (ex. Dispatcher)

## Карточка сервиса

<table data-header-hidden data-full-width="true"><thead><tr><th width="304"></th><th></th></tr></thead><tbody><tr><td>Название сервиса</td><td>ulms</td></tr><tr><td>Система</td><td><a data-mention href="../sistemy/mediaservisy.md">mediaservisy.md</a></td></tr><tr><td>Ответственная команда</td><td></td></tr><tr><td>Репозиторий</td><td><a href="https://github.com/foxford/ulms-backend/tree/main/ulms">https://github.com/foxford/ulms-backend/tree/main/ulms</a></td></tr><tr><td>Язык программирования</td><td>Rust</td></tr><tr><td>Статус</td><td> <mark style="background-color:green;">Production</mark> </td></tr></tbody></table>

## Описание

Центральный сервис медиасервисов: предоставляет публичное API для портала Фоксфорд и конечных пользователей. ULMS обеспечивает весь жизненый цикл онлайн-класса от его создания, проведения, и до готовности записи.



## Схема работы

```mermaid fullWidth="false"
graph TD
  subgraph Foxford
    User((User)) ---> ULMS
    Stoege -- create\nclassroom ---> ULMS
    ULMS -- authz\nrequest --> Stoege

    subgraph "Эти сервисы объединятся в один сервис ULMS"
      Tq -. authz\nrequest .-> ULMS
      Conference -. authz\nrequest .-> ULMS
      Event -. authz\nrequest .-> ULMS
      Storage -. authz\nrequest .-> ULMS
     
      ULMS

      ULMS -- create\ntask ---> Tq
    end

    subgraph "NATS JetStream заменит VerneMQ"
      ULMS .-> VerneMQ[["Verne MQ"]]
      ULMS ----> NatsJetStream[["NATS JetStream"]]
    end

    ULMS ----> Redis[(Redis)]
    ULMS ----> PostgreSQL[(PostgreSQL)]
  end
```

