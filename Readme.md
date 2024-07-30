```mermaid
erDiagram
    COORDENADOR {
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
        boolean status
        string coordinator_id FK
    }

    DEV {
        string id PK
        string name
        string photo
        string project_id FK
    }

    ANJO {
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

    COORDENADOR ||--o{ PROJECT: "1, cadastra N"
    PROJECT ||--o{ DEV: "1, tem N"
    PROJECT ||--o{ ANGEL: "1, tem N"
    PROJECT ||--o{ PROJECT_CATEGORY: "1, tem N"
    CATEGORY ||--o{ PROJECT_CATEGORY: "1, tem N"
    COORDENADOR ||--o{ DEV: "1, cadastra N"
    COORDENADOR ||--o{ ANGEL: "1, cadastra N"
