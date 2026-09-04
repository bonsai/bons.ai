# bons.ai — Agent OS

**bons.ai is the Agent OS for the Bonsai agent organization.**

It provides the operating layer that connects agents, sessions, memory, tools, workflows, and GitHub-based shared state.

## System model

```text
                 bons.ai
                Agent OS
                    │
       ┌────────────┼────────────┐
       │            │            │
    Agents       Sessions      Tools
       │            │            │
       │         HOIPOI          │
       │        4D Pocket         │
       │            │            │
       └──────────recap.json─────┘
                    │
                 GitHub
                    │
                   AW
                    │
              Agent execution
```

## Core components

- **Agent** — participant / worker
- **Session** — unit of ongoing work
- **HOIPOI** — portable session capsule / 4D pocket
- **recap.json** — machine-readable session state and handoff protocol
- **GitHub** — shared memory, artifacts, transport
- **AW** — Agentic Workflow orchestration / execution
- **ADR** — durable decision memory
- **Issue** — task / work queue
- **PR** — implementation artifact

## Relationship

```text
Chat Session
    ↓
  HOIPOI
    ↓
recap.json
    ↓
 bons.ai
    ↓
 GitHub / AW
    ↓
 Agents
```

**bons.ai = OS**  
**HOIPOI = pocket**  
**recap.json = capsule**  
**AW = scheduler/orchestrator**  
**GitHub = shared filesystem + message bus**

## Inventory

```yaml
id: bons-ai
name: bons.ai
display_name: Bonsai Agent OS
type: agent-os
status: active
components:
  - agents
  - sessions
  - hoipoi
  - recap.json
  - github
  - agentic-workflows
```
