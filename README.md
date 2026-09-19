# bons.ai

**bons.ai is one Agent in the Bonsai world.**

It is not an Agent OS above other repositories. Each repository is an Agent; bons.ai is one of them.

## Model

```text
repo = Agent
agent.md = Agent declaration
list = Agent collection
Skill = Agent capability
System = relation / cooperation between Agents
World = field in which Agents exist
```

The basic rule is:

> **1 repo = 1 Agent**

Every Agent describes itself with `agent.md`.

## bons.ai

bons.ai exists to connect people, repositories, skills, sessions, and interfaces through a shared GitHub-centered working environment.

It observes the world, thinks, forms hypotheses, acts, and observes again.

```text
World
  ↓
observe
  ↓
think
  ↓
hypothesis
  ↓
action
  ↓
World'
  ↓
observe
  ↺
```

## Agent

An Agent has complementary aspects:

- **Entity / 実体** — the repository and its contents
- **Behavior / 挙動** — what it does
- **Awareness / 意識** — what it notices and cares about

These are not separate layers. They are complementary aspects of one Agent.

See [`agent.md`](agent.md) for bons.ai's self-declaration.

## Skills

A Skill is an Agent capability.

Skills are not limited to executable actions. Thinking capabilities such as observing, classifying, hypothesizing, and reasoning can also be Skills.

## Relations

Agents cooperate through relationships.

```text
Agent ←→ Agent
   ↕
 System
   ↕
World
```

A System is therefore a relation among Agents, not a higher-level Agent.

## Lists

Lists are the exception to the 1-repo-1-agent rule.

A list may enumerate Agents, but it does not become an Agent merely by containing Agent references.

```text
agents.yaml
agents.json
agents.md
    ↓
Agent list
```

## GitHub

GitHub is the canonical shared state.

- repository = Agent
- `agent.md` = self-declaration
- Issue = work
- PR = implementation artifact
- Actions / AW = execution
- list = collection / index

The repository itself remains the source of truth.

## Principle

> **1 repo = 1 Agent.**

> **bons.ai is one Agent among Agents.**