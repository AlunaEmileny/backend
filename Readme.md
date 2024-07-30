```mermaid
erDiagram
    USER {
        string id PK
        string name
        string email
        string password
        datetime createDateTime
        datetime updateDateTime
    }

    PROJECT {
        string id PK
        string name
        string descricao
        string banner
        datetime createDateTime
        datetime updateDateTime
        enum status {"em andamento", "concluido"}
        string coordinator_id FK
    }

    DEV {
        string id PK
        string name
        string photo
        string project_id FK
    }

    ANGEL {
        string id PK
        string name
        string photo
        string project_id FK
    }

    CATEGORY {
        string id PK
        string name
    }

    PROJECT_CATEGORY {
        string project_id FK
        string category_id FK
    }

    USER ||--o{ PROJECT: "cadastra"
    PROJECT ||--o{ DEV: "tem"
    PROJECT ||--o{ ANGEL: "tem"
    PROJECT ||--o{ PROJECT_CATEGORY: "tem"
    CATEGORY ||--o{ PROJECT_CATEGORY: "tem"
    USER ||--o{ DEV: "cadastra"
    USER ||--o{ ANGEL: "cadastra"
