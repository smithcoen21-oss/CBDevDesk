# CBDevDesk Phase 2

GitHub-ready foundation for CBDevDesk: JWT authentication, project RBAC, PostgreSQL metadata, Redis, Yjs/Socket.IO collaboration, a React/CodeMirror editor, project files, Git commits/history, CI, and a deliberately disabled-by-default execution boundary.

## Quick start

Requirements: Docker and Docker Compose.

```bash
cp .env.example .env
docker compose up --build
```

Open `http://localhost:5173`.

## Architecture

React + CodeMirror + Yjs -> Socket.IO collaboration service -> Redis/PostgreSQL

Flask API -> PostgreSQL + project workspace + Git

Optional code execution must run in a separate hardened worker. Never expose the Docker socket to the web/API service.

## Important

This is a production-oriented foundation, not a claim that arbitrary code execution is safe by default. Before enabling untrusted execution, add OS/container isolation, CPU/memory/PID/disk/time limits, syscall restrictions, network policy, image controls and security testing.
