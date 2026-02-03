# Exercise 0.5: Single Page App Diagram

This diagram shows the sequence of events when the user goes to the SPA version of the notes app at 

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Navigate to /spa
## 🔹 Workflow
    Browser->>Server: GET /spa (HTML shell)
    Server-->>Browser: HTML with <div id="root"> and JS
    Browser->>Server: GET /main.css
    Server-->>Browser: CSS file
    Browser->>Server: GET /main.js
    Server-->>Browser: JavaScript bundle
    Browser->>Server: GET /data.json
    Server-->>Browser: JSON notes data
    Browser->>Browser: React/JS renders notes dynamically
