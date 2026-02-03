# Exercise 0.6: New Note in Single Page App Diagram

This diagram shows the sequence of events when the user creates a new note in the SPA version of the notes app.

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Type note and click submit
    Browser->>Browser: Intercept form submit event
    Browser->>Server: POST /new_note_spa (JSON payload)
    Server-->>Browser: 201 Created (confirmation)
    Browser->>Browser: Update DOM immediately with new note
    Browser->>Server: GET /data.json (fetch updated notes list)
    Server-->>Browser: JSON notes data
    Browser->>Browser: Render updated notes list dynamically
