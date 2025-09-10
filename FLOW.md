# 📈 Collaborative Event Flow

Below is a simplified sequence diagram showing how two users, Alice and Bob, collaborate to schedule an event.

---

```mermaid
sequenceDiagram
    participant Alice as Alice
    participant Backend as Backend
    participant Bob as Bob

    %% 1. Alice creates an event
    Alice->>Backend: Create "Study Session" Event
    Backend-->>Alice: Confirm Event Created

    %% 2. Alice invites Bob
    Alice->>Backend: Invite Bob
    Backend-->>Bob: Send Invitation Notification

    %% 3. Bob proposes a new time
    Bob->>Backend: Propose New Time (6 PM)
    Backend-->>Alice: Notify Proposal

    %% 4. Alice accepts proposal
    Alice->>Backend: Accept Proposal
    Backend-->>Bob: Notify Event Updated

    %% 5. Bob confirms participation
    Bob->>Backend: Accept Invitation
    Backend-->>Alice: Notify Participation Confirmed
```

---

## 📝 Flow Steps

1. **Event Creation:** Alice creates an event.
2. **Invitation:** Alice invites Bob.
3. **Proposal:** Bob suggests a new time.
4. **Acceptance:** Alice accepts the new time.
5. **Confirmation:** Bob confirms his participation.

---
