# Exercise 0.4: New Note Diagram

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Submit new note
    Browser->>Server: POST /new_note_spa (JSON)
    Server-->>Browser: 201 Created
    Browser->>Browser: Update DOM with new note
    Browser->>Server: GET /data.json
    Server-->>Browser: JSON notes data
    Browser->>Browser: Render updated notes list

