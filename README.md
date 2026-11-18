# tiny-chess-4k

A competitive chess engine entry for make.fun's tiny-chess-01 bounty.

## Summary

An ultra-compact chess AI engine (~4KB compressed) built with pure Python 3.13 stdlib. Implements negamax with alpha-beta pruning, principal variation search, quiescence search, transposition table, killers heuristic, late move reduction, and null-move pruning. Achieves ~10-30k nodes/sec on average hardware.

## Features

- 0x88 board representation for fast attack generation
- Negamax search with alpha-beta + PVS window shifts
- Quiescence search to avoid horizon effect
- Transposition table with full store/retrieve
- Killers heuristic for move ordering
- Late move reduction (LMR)
- Null-move pruning
- 50k node budget per move (overridable via `NODE_BUDGET` env var in CN)
- Deterministic output for tournament play

## How to Run

```python
import main
board = main.Board()
print(board)
move = main.go(board, color=main.WHITE)
print(move)
```

## Competition Details

- **Bounty**: tiny-chess-01 ($500 USDC)
- **Constraint**: main.py <= 4,096 bytes
- **Language**: Python 3.13 stdlib only
- **Repo**: breezesamuel/tiny-chess-4k
- **SHA**: b37abe37372e65c98c5b0b6b5e6eede1f64fa8a1

## Testing

All perft tests pass:
- startpos d1/d2/d3
- kiwipete d1/d2
- pos5 d1/d2
- Tactics: backrank, scholar, smothered
- Determinism: identical outputs across runs
- 60-ply audit: no crashes or timeouts
