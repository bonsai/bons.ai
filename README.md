# bons.ai — Agent OS

**bons.ai is the Agent OS for the Bonsai agent organization.**

It provides the operating layer that connects agents, sessions, memory, tools, workflows, and GitHub-based shared state.

## World model

bons.ai treats the world as a typed, relational world.

The world is described through five layers:

```text
Dictionary
    ↓
Ontology
    ↓
Type
    ↓
System
    ↓
Interface
```

- **Dictionary — 言葉**: defines the meaning of terms and symbols.
- **Ontology — 存在**: defines what exists in the world.
- **Type — 型**: defines the structure and kind of entities.
- **System — 関係**: describes relationships between entities.
- **Interface — 境界と接続**: defines where entities meet the outside world and what is exchanged across that boundary.

```text
Dictionary = 言葉
Ontology   = 存在
Type       = 型
System     = 関係
Interface  = 境界と接続
```

Boundary is not treated as a separate layer:

```text
Interface = Boundary + Exchange
```

This gives bons.ai a world model in which entities have types, entities are related by systems, and entities interact with their environment through interfaces.

## Autonomous agent loop

bons.ai is autonomous: it observes, thinks, forms hypotheses, experiments, acts, and observes again.

```text
World
  ↓
observe
  ↓
think
  ↓
hypothesis
  ↓
experiment
  ↓
action
  ↓
World'
  ↓
observe
  ↺
```

The agent is **hypothesis driven**. A hypothesis is treated as a testable knowledge state rather than merely a thought memo.

```text
observation
    ↓
hypothesis
    ↓
prediction
    ↓
experiment
    ↓
evidence
    ↓
evaluation
    ↓
update
    ↺
```

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

## Vision — prompt → product

bons.ai は、**プロンプトからプロダクトまで**を一貫させる Agent OS。

```text
prompt
  ↓
相談（consult）
  ↓
設計書（design doc）
  ↓
ルール（rules）
  ↓
product
```

**相談してから設計する。設計してから作る。作る前にルールを決める。**

## Design Principles

- **Consult first.** 相談してから設計書を書く。
- **Rules over prompts.** ルールを作る。場当たりのプロンプトに頼らない。
- **Prune the waste.** 無駄は刈り取る。
- **Agents initiate.** エージェントから働きかける（待たない）。
- **CLI first.** 操作は CLI から。
- **Wrapper skills.** スキルをラップして呼び出す。
- **gh aw for CI/CD.** Agentic Workflows で pack / publish / deploy。
- **MCP + SDK.** MCP サーバと SDK を提供する。
- **OpenAPI.** API は OpenAPI で定義する。
- **Natural language first.** 実装は Python / TypeScript / Rust / Go を想定するが、**今は自然言語のみ**。
- **Bilingual.** 英語と日本語を混ぜて書く。
- **Start small.** まず **README と issue 10本**のみ。既存 repo のオーガナイズ計画を先に行う。

## Conceptual model — Verbs, Ontology, Interfaces

- **体験は動詞で語られる。** Experience is narrated by verbs.
- **動詞はオントロジで関係される。** Verbs are related through ontology.
- **動詞を持つエージェントはチームを作る。** Agents with verbs form teams → ecosystem.
- **界面で異なる型たちが交流する。** At interfaces, different types interact.
- **物理層と記号層を統一する。** Unify the physical layer and the symbolic layer.
- **type はオブジェクトに限らない。** Type spans objects, verbs, agents, workflows, relations, interfaces.

```text
Experience → Verb → Ontology → Agent → Team → Ecosystem
                                   ↕
                              Interface
                                   ↕
                     Physical layer  ⇄  Symbolic layer
```

```text
TYPE
 ├─ Object Type      名詞
 ├─ Verb Type        動詞（体験を語る）
 ├─ Agent Type       動詞を持つエージェント
 ├─ Workflow Type    動詞の連鎖
 ├─ Relation Type    関係（オントロジ）
 └─ Interface Type   型が交流する界面
```

## X Series

The Bonsai layers are organized as the **X Series** (A–Z) and indexed in
[`bonsai/xX`](https://github.com/bonsai/xX): `xX` (foundation), plus `AX`, `BX`,
`CX`…`ZX`. Types (philosopher, scientist, businessperson, …) and transformations
(market, editor, writing, traveler, …) are specializations of the same base.

See [`bonsai/OX`](https://github.com/bonsai/OX) for the type system (Type OS),
and [`bonsai/TX`](https://github.com/bonsai/TX) for Traveler X.

## AGENTS / SESSIONS / MEMORY

```text
Agent   = who acts        （誰が行為するか）
Session = unit of work    （仕事の単位）
HOIPOI  = pocket          （持ち運べるセッション）
recap   = capsule         （機械可読な引き継ぎ）
GitHub  = shared state    （共有された状態）
AW      = orchestration   （実行の調整）
```

## Roadmap

| 段階 | 内容 |
|---|---|
| now | README と issue 10本のみ |
| next | 既存 repo のオーガナイズ |
| later | CLI / skills / MCP / SDK / OpenAPI |
| later | ブラウザ拡張（WebSocket） |
|
