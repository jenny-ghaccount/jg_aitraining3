# Cloud Architecture Overview

```mermaid
## Cloud Architecture Overview

```mermaid
architecture-beta
    group frontend(cloud)[Frontend]
    group backend(cloud)[Backend]

    service user(internet)[User]
    service reactapp(server)[React App] in frontend
    service apiserver(server)[API Server] in backend
    service inmemorydb(database)[InMemoryDB] in backend

    user:R -- L:reactapp
    reactapp:R -- L:apiserver
    apiserver:B -- T:inmemorydb
```

## Sequence: User Creates a TODO

```mermaid
sequenceDiagram
    participant User
    participant Frontend as React App
    participant Backend as API Server
    participant DB as InMemoryDB

    User->>Frontend: Open app, fill TODO form
    Frontend->>Backend: POST /api/tasks (new TODO)
    Backend->>DB: Insert TODO
    DB-->>Backend: Confirm insert
    Backend-->>Frontend: Respond with created TODO
    Frontend-->>User: Show new TODO in list
```
```mermaid
sequenceDiagram
    participant User
    participant Frontend as React App
    participant Backend as API Server
    participant DB as InMemoryDB

    User->>Frontend: Open app, fill TODO form
    Frontend->>Backend: POST /api/tasks (new TODO)
    Backend->>DB: Insert TODO
    DB-->>Backend: Confirm insert
    Backend-->>Frontend: Respond with created TODO
    Frontend-->>User: Show new TODO in list
```
