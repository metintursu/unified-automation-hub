# Unified Automation Hub

A local, Docker-based hub that combines industrial data flows, AI agents and lean-manufacturing automation in one stack.

> **Status:** early release. Designed for local development and experimentation. Do not expose it to the internet without hardening it first.

## Services

| Service | Purpose | Default port |
|---|---|---|
| Node-RED | Industrial data flows, UNS simulation, alarms | 1881 |
| n8n | Autonomous workflows and AI-assisted automation | 5680 |
| Langflow | AI agent builder | 7862 |
| Ollama | Local LLM runtime | 11435 |
| InfluxDB 2.x | Time-series telemetry | 8087 |
| Grafana | Real-time factory dashboards | 3003 |
| EMQX | MQTT broker (dashboard on 18084) | 1884 |
| PostgreSQL | Relational database (used by n8n) | 5433 |

## Quick start

Requirements: Docker Desktop (or Docker Engine with Compose v2).

1. Copy the example environment file:
   `cp .env.example .env` (Windows PowerShell: `Copy-Item .env.example .env`)
2. Open `.env` and replace every `CHANGE_ME` with a strong, unique value.
3. Start the stack: `docker compose up -d`
4. Open the services from the table above, for example `http://localhost:3003` for Grafana.

Example workflows are in `uah-n8n-full-workflow.json` and `uah_import.json`. Import them from the n8n interface.

## Security notes

- Never commit your `.env` file. It is listed in `.gitignore`.
- Use strong passwords and tokens.
- Change default credentials of every service after the first start.

## Roadmap

- [x] Pin container image versions
- [x] Bind ports to localhost by default
- [ ] Health checks for all services
- [ ] Persistent storage for the EMQX broker
- [ ] Predictive-maintenance and lean-production example flows

## License

To be added.

