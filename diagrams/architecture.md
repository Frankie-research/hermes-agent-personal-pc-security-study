# Logical architecture

```mermaid
flowchart TD
    U[Authorized User / Telegram Client] --> G[Hermes Gateway / Agent Core
    auth | sessions | cron | delivery]
    G --> M[Model / API]
    G --> C[Cron definitions + fixed scripts]
    G --> S[Docker Terminal Sandbox
isolation / least privilege]
    S --> D[Minimal project data]
    S --> N[External data (RO)
NAS / share]
    D --> O[Email / Telegram
delivery only]
    N --> O
```

The public diagram intentionally omits private usernames, IP addresses, credentials, bot identifiers and absolute file paths.
