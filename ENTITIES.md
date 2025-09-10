# 📊 Entity Relationship Diagram

The following diagram and entity definitions describe the core data model for the Collaborative Personal Scheduler. This enhanced version improves clarity, adds missing relationships, and uses consistent naming and comments.

---

```mermaid
erDiagram
    USER ||--o{ EVENT : "creates"
    USER ||--o{ EVENTPARTICIPANT : "participates in"
    EVENT ||--o{ EVENTPARTICIPANT : "has participants"
    EVENT ||--o{ PROPOSAL : "can have"
    PROPOSAL ||--o{ PROPOSALRESPONSE : "collects responses"
    USER ||--o{ PROPOSAL : "proposes"
    USER ||--o{ PROPOSALRESPONSE : "responds"
    USER ||--o{ NOTIFICATION : "receives"
    USER ||--o{ EMAILLOG : "sent to"
    USER }|..|{ ROLE : "assigned"
    EVENT ||--o{ RECURRINGRULE : "follows"

    USER {
      bigint id PK "Primary key"
      varchar username "Unique username"
      varchar email "User email address"
      varchar password "Hashed password"
      timestamp created_at "Account creation time"
    }

    ROLE {
      bigint id PK "Primary key"
      varchar name "Role name (user/admin)"
    }

    EVENT {
      bigint id PK "Primary key"
      varchar title "Event title"
      text description "Event description"
      timestamp start_time "Start time"
      timestamp end_time "End time"
      varchar category "Category (work/personal/study)"
      bigint created_by FK "Created by USER"
    }

    EVENTPARTICIPANT {
      bigint id PK "Primary key"
      bigint event_id FK "Linked EVENT"
      bigint user_id FK "Linked USER"
      varchar status "INVITED, ACCEPTED, DECLINED"
    }

    RECURRINGRULE {
      bigint id PK "Primary key"
      bigint event_id FK "Linked EVENT"
      varchar frequency "DAILY, WEEKLY, MONTHLY"
      int interval "Repeat interval"
      date until_date "Repeat until date"
    }

    PROPOSAL {
      bigint id PK "Primary key"
      bigint event_id FK "Linked EVENT"
      bigint proposer_id FK "Proposed by USER"
      timestamp proposed_time "Suggested time slot"
    }

    PROPOSALRESPONSE {
      bigint id PK "Primary key"
      bigint proposal_id FK "Linked PROPOSAL"
      bigint user_id FK "Responding USER"
      varchar response "ACCEPT, REJECT"
    }

    NOTIFICATION {
      bigint id PK "Primary key"
      bigint user_id FK "Recipient USER"
      varchar message "Notification message"
      timestamp created_at "Notification time"
      boolean read "Read status"
    }

    EMAILLOG {
      bigint id PK "Primary key"
      bigint user_id FK "Recipient USER"
      varchar subject "Email subject"
      timestamp sent_at "Sent time"
    }
```

---

## 📝 Entity Highlights

- **USER:** Core user profile, linked to events, proposals, notifications, and roles.
- **ROLE:** Supports role-based access (user/admin).
- **EVENT:** Calendar event with category, creator, and recurrence.
- **EVENTPARTICIPANT:** Tracks user participation and status for events.
- **RECURRINGRULE:** Defines event repetition patterns.
- **PROPOSAL:** Suggests alternative time slots for events.
- **PROPOSALRESPONSE:** Collects user responses to proposals.
- **NOTIFICATION:** In-app alerts for users.
- **EMAILLOG:** Tracks sent emails for auditing and troubleshooting.

---

> For further details on API usage and business logic, refer to the documentation files in this repository.
