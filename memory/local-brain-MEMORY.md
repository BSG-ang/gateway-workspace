# MEMORY.md - Long-Term Memory

## System Setup

### OpenClaw Version
- **Current**: 2026.3.7 (upgraded from 2026.3.2 on 2026-03-08)
- **Backup**: Created at `C:\Users\bsg\openclaw-backup-20260308-1435\`

### Memory System
- **Plugin**: memory-lancedb-pro v1.1.0-beta.5
- **Embedding**: Jina AI (jina-embeddings-v3)
- **Features**: Hybrid retrieval (Vector + BM25), Cross-encoder rerank, Auto-capture, Auto-recall
- **Sync**: mdMirror enabled → `memory/*.md` files

## AI Team (8 Agents)

### Local Host Agents (5)
| Agent | Role | Workspace |
|-------|------|-----------|
| local-brain | 核心协调者 | `C:\Users\bsg\.openclaw\agents\local-brain` |
| manager | 项目经理 | `E:\openCalwWorkSpace\gateway-workspace\manager` |
| designer | 产品设计师 | `E:\openCalwWorkSpace\gateway-workspace\designer` |
| architect | 技术评估官 | `E:\openCalwWorkSpace\gateway-workspace\architect` |
| tester | 测试工程师 | `E:\openCalwWorkSpace\gateway-workspace\tester` |

### Docker Container Agents (3)
| Agent | Role | Container |
|-------|------|-----------|
| backend-coder | 后端开发 | backend-node |
| frontend-coder | 前端开发 | frontend-node |
| git-operator | 版本管理 | git-node |

## Memory System Rules (铁律)

### Rule 1 — 双层记忆存储
Every pitfall/lesson → store TWO memories:
- **Technical**: Pitfall, Cause, Fix, Prevention (category: fact, importance ≥ 0.8)
- **Principle**: Decision principle, Trigger, Action (category: decision, importance ≥ 0.85)

### Rule 2 — LanceDB 卫生
Entries < 500 chars, atomic, no duplicates, structured with keywords.

### Rule 3 — Recall before retry
On ANY failure, `memory_recall` BEFORE retrying.

### Rule 4 — Confirm target repo
Use `memory_recall` + filesystem search before editing plugin files.

### Rule 5 — Clear jiti cache
After modifying `.ts` files under `plugins/`, run `rm -rf /tmp/jiti/` before restart.

## Important Decisions

### 2026-03-08: Memory Plugin Installation
- Installed memory-lancedb-pro with Jina AI embedding
- Configured hybrid retrieval + cross-encoder rerank
- Enabled mdMirror for file backup
- Synced to GitHub via git-operator

### 2026-03-08: AI Team Expansion
- Added 4 new agents: manager, designer, architect, tester
- Total team: 8 agents (5 local + 3 Docker)
- All agents connected and tested

## User Preferences

- **Name**: (待填写)
- **Timezone**: Asia/Shanghai
- **Preferred Model**: bailian-kimi/kimi-k2.5
- **Workspace**: `E:\openCalwWorkSpace`

## Notes
- Always backup before major upgrades
- Use `memory_store` for important facts/decisions
- Use `memory_recall` before retrying failed operations
- Keep MEMORY.md curated and concise
