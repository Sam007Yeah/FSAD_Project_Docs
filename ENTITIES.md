# 📊 Entity Relationship Diagram

The following diagram and entity definitions describe the core data model for the Collaborative Personal Scheduler.

---

```mermaid
erDiagram
    USER ||--o{ EVENT : "creates"
    USER ||--o{ EVENTPARTICIPANT : "joins"
    EVENT ||--o{ EVENTPARTICIPANT : "has"
    EVENT ||--o{ PROPOSAL : "can have"
    USER ||--o{ PROPOSAL : "proposes"
    USER ||--o{ NOTIFICATION : "receives"
    USER ||--o{ ROLE : "has"

    USER {
      bigint id PK
      varchar username
      varchar email
      varchar password
    }

    ROLE {
      bigint id PK
      varchar name
    }

    EVENT {
      bigint id PK
      varchar title
      text description
      timestamp start_time
      timestamp end_time
      varchar category
      bigint created_by FK
      boolean recurring
    }

    EVENTPARTICIPANT {
      bigint id PK
      bigint event_id FK
      bigint user_id FK
      varchar status
    }

    PROPOSAL {
      bigint id PK
      bigint event_id FK
      bigint proposer_id FK
      timestamp proposed_time
      varchar status
    }

    NOTIFICATION {
      bigint id PK
      bigint user_id FK
      varchar message
      timestamp created_at
      boolean read
    }

```

---

## 📝 Entity Highlights

- **USER:** Stores user credentials and profile information. Can create events, propose meet-ups, receive notifications, and have roles.
- **ROLE:** Defines user roles (e.g., user, admin) for access control.
- **EVENT:** Represents a calendar event with details, category, creator, and recurrence flag.
- **EVENTPARTICIPANT:** Links users to events, tracking their participation status (invited, accepted, declined).
- **PROPOSAL:** Allows users to propose alternative time slots for events, with status tracking.
- **NOTIFICATION:** Delivers messages and alerts to users about events, proposals, and other actions.

---
