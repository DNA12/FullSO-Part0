```mermaid
sequenceDiagram
participant browser
participant server

browser->>server: Submission of note
activate server
Note over server: Javascript code appends note to notes list. Updates unordered list
server->>browser: Resends notes list back via POST /new_note_spa
deactivate server

browser->>browser: Clear existing note list
browser->>browser: Extract notes data from the JSON response
browser->>browser: Renders updated note list on the page
```
