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

---

## 🔹 Explanation
- **User action**: Submits a new note.  
- **Browser intercepts**: JavaScript prevents full page reload.  
- **AJAX request**: Browser sends `POST /new_note_spa` with note data in JSON.  
- **Server response**: Confirms creation with `201 Created`.  
- **DOM update**: Browser immediately adds the new note to the list.  
- **Data refresh**: Browser fetches `/data.json` to ensure the list is up to date.  
- **Rendering**: Notes list is re‑rendered dynamically without leaving the SPA.

