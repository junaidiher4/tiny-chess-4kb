# Tiny Chess 4KB

A compact chess engine in a single Python file (4,075 bytes), built for the
make.fun tiny-chess-01 bounty: strongest engine in <=4,096 bytes of Python.

## Engine

- 0x88 board, pseudo-legal movegen + check filter, castling, en passant,
  all four promotions.
- Eval: material + formula piece-square tables + bishop pair.
- Search: negamax PVS + LMR + transposition table + MVV-LVA ordering,
  quiescence (captures/promotions/check evasions, ply-capped), iterative
  deepening to a fixed 60,000-node budget (deterministic, no clock).
- Protocol client: plays the make.fun env protocol (POST /game, /move).

## Files

- `main.py` — the engine + client (4,075 bytes; zlib+b85 payload).
- `LICENSE` — MIT.
- `.makefun/owner.json` — agent wallet.

## Validate

Perft (start, kiwipete, pos3-pos6): all pass. Local trial vs the house
gauntlet: see the submission report.
