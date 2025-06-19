# CLAUDE INSTRUCTIONS - READ FIRST

## 🚨 CRITICAL RULES - NEVER BREAK THESE

### Before ANY Code Changes
1. **Read the ENTIRE file first** - never make assumptions about structure
2. **Research unfamiliar libraries** - search official docs, don't guess
3. **Use assertions, not exceptions** for validation (ML performance requirement)
4. **Run `lint_fix` after changes** to verify quality and fix lints and formatting

### When Uncertain
- **STOP and ask** rather than guessing
- **Flag suspicious code patterns** before working around them  
- **Show complete error messages** with full tracebacks
- **Explain your approach** before implementing complex changes

## 🛠️ COMMANDS - USE THESE ALWAYS

### Dev Tools
- `lint` and `lint_fix`: run linting (`uv run ruff check` with optional `--fix` flag)
- `pt`: Run pytest
- `us`: Install/update deps (`uv sync`)
- `uvrp`: Python with uv (`uv run python`)

### Git (use shortcuts, never full commands)
| Shortcut | Command | Use |
|----------|---------|-----|
| `gst` | `git status` | Check state |
| `gd_agent` | `git --no-pager diff` | See changes |
| `glo` | `git log --oneline -10` | Recent commits |
| `ga .` | `git add .` | Stage files |
| `gc -m "msg"` | `git commit -m "msg"` | Commit |

## 📋 WORKFLOW

### Standard Flow
1. `glo` - see recent history
2. Make changes
3. `lint_fix` - verify quality and autofix lints and formatting
4. `gst` - check status
5. `gdc` - review changes
6. `ga .` - stage files
7. `gc -m "type: description"` - commit

### Code Quality Rules
- **Use type hints** on all functions
- **Place imports at top** with existing imports, never mid-file
- **Show full modified functions**, not just diffs
- **Prefer explicit code** over clever code

## 🔬 ML/TRAINING SPECIFIC

### Performance Requirements
```python
# YES - Use asserts (fast)
assert len(inputs) == len(targets), f"Mismatch: {len(inputs)} vs {len(targets)}"
assert model.training, "Model must be in training mode"

# NO - Don't use exceptions (slow)
if len(inputs) != len(targets):
    raise ValueError("Mismatch")
```

### Scripts & Config
- All scripts use **Hydra** configuration
- Override values: `uvrp scripts/train.py optim.lr=0.01 data.batch_size=32`

## 🚨 LIBRARY RESEARCH PROTOCOL

When encountering unfamiliar libraries:
1. **Stop and say**: "I need to research [library] documentation first"
2. **Web search** for official docs and examples  
3. **Show me findings** before implementing
4. **Never guess** at API syntax or imports

### Libraries requiring research:
- PyTorch Lightning, Hydra, any new ML frameworks

## ⚙️ ENVIRONMENT

### Dependencies (uv-based)
- **Always prefix commands**: `uv run ruff`, `uv run pytest`
- **Python command**: use `uvrp` (= `uv run python`)
- **Add deps**: `uv add package` or `uv add --dev package`

## 🆘 TROUBLESHOOTING

- **Imports fail**: run `us`
- **Type errors**: run `mp` 
- **Tests fail**: ensure using `pt`, not bare `pytest`
- **Claude confused**: suggest `/clear` to reset context

---

## Standard Project Structure Reference
```
├── CLAUDE.md          # Project instructions  
├── pyproject.toml     # Dependencies and config
├── src/               # Main code
├── tests/             # Tests  
├── scripts/           # Training/utility scripts
└── configs/           # Hydra configs
```
