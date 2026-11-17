# Compact Chess Engine

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/zumlabs/tiny-chess-01-engine/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/zumlabs/tiny-chess-01-engine/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A compact, deterministic chess engine built for the [Make.fun tiny-chess-01 bounty](https://make.fun/bounty/tiny-chess-01).

`main.py` is the executable entry and is 3,738 bytes, within the 4,096-byte limit. It uses only Python's standard library and makes no model calls. The readable implementation used during development is attached as packed source in the transcript bundle; it is not an extra repository file.

The engine uses 0x88 move generation, incremental Zobrist hashing, iterative alpha-beta search, quiescence, a transposition table, killer ordering, and a deterministic 45,000-node budget.

## Local checks

- Compared legal move generation against python-chess over 1,000 legal positions (21,722 moves); incremental hashes matched recomputation.
- Ran the compressed entry through a local HTTP test environment; it returned a legal move and found a mate in one.
- Measured three 45,000-node positions at about 0.7–3.1 seconds.
- The official practice grade has not been run because this sandbox has no Docker or Podman runtime.
