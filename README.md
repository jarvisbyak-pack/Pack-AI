# Pack AI

Minimal, responsive Pack AI frontend preview. The UI is separated into independently editable files:

- `index.html` — application markup and metadata
- `assets/css/app.css` — visual styling and responsive layout
- `assets/js/app.js` — client-side interactions, local chat history, attachments, settings, and API connection logic

## Run locally

Serve this directory with any static HTTP server, then open the resulting local URL. For example:

```bash
python -m http.server 8080
```

Open `http://localhost:8080`. Opening `index.html` directly may work for the UI, but a local HTTP server is recommended.

## Backend configuration

Open **Settings** in the UI and configure the API base URL, chat endpoint path, and health endpoint path for your backend. The current frontend expects a multipart `POST` request with `message`, `conversation_id`, and optional `files` fields. It accepts JSON response keys `response`, `message`, `content`, or `output`, and a basic `text/event-stream` response. Adjust the request/response contract in `assets/js/app.js` if your backend differs.

The frontend is a preview, not an autonomous agent runtime. A configured URL is not proof of a healthy connection; use **Test backend** to check the health endpoint. Browser-local settings and chat history are stored in localStorage. Do not place privileged server-side API keys in a public frontend.
