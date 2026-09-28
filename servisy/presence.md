# Presence

## Карточка сервиса

<table data-header-hidden data-full-width="true"><thead><tr><th width="304"></th><th></th></tr></thead><tbody><tr><td>Название сервиса</td><td>presence</td></tr><tr><td>Система</td><td><a data-mention href="../sistemy/mediaservisy.md">mediaservisy.md</a></td></tr><tr><td>Ответственная команда</td><td></td></tr><tr><td>Репозиторий</td><td><a href="https://github.com/foxford/ulms-backend/tree/main/presence">https://github.com/foxford/ulms-backend/tree/main/presence</a></td></tr><tr><td>Язык программирования</td><td>Rust</td></tr><tr><td>Статус</td><td> <mark style="background-color:green;">Production</mark> </td></tr></tbody></table>

## Описание

Ведет список активных пользователей и обеспечивает доставку пользовательских нотификаций в веб-приложения.

## Схема работы

```mermaid fullWidth="false"
graph TD
  subgraph Foxford
    NatsJetStream[[Nats JetStream]] -- user\nnotifications --> Presence

    Presence

    Presence -- user\nnotifications ---> User((User))
    Presence --> PostgreSQL[(PostgreSQL)]
  end


```

