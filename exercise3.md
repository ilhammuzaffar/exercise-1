```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.h+elsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "notes": "mancing mania", "date": "2023-1-1" }, ... ]
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/new_notes_spa
    activate server
    server-->>browser: [{"content":"e","date":"2024-03-04T17:33:32.662Z"}, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes
```