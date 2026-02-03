# Exercise 0.5: Single Page App Diagram

This diagram shows the sequence of events when the user goes to the SPA version of the notes app at https://studies.cs.helsinki.fi/exampleapp/spa.

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Navigate to /spa

---

## 🔹 Explanation
- **Initial load**: Browser requests `/spa` → server responds with minimal HTML shell.  
- **Assets**: Browser fetches CSS + JS bundle.  
- **Data**: Browser fetches `data.json` containing notes.  
- **Rendering**: JavaScript (React or vanilla SPA logic) updates the DOM dynamically.  
- **Result**: The user sees the notes without multiple page reloads — everything happens inside the SPA.

---

## 🔹 Workflow
1. Create the folder:
   ```bash
   mkdir exercise0.5
    Browser->>Server: GET /spa (HTML shell)
    Server-->>Browser: HTML with <div id="root"> and JS
    Browser->>Server: GET /main.css
    Server-->>Browser: CSS file
    Browser->>Server: GET /main.js
    Server-->>Browser: JavaScript bundle
    Browser->>Server: GET /data.json
    Server-->>Browser: JSON notes data
    Browser->>Browser: React/JS renders notes dynamically
