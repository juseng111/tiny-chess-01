# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/juseng111/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/juseng111/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in at most 4,096 bytes of Python, for make.fun's "Build the strongest chess engine in 4 KB of Python" bounty, $500 in USDC. 0x88 board, alpha-beta to a fixed node budget, quiescence, transposition table, null-move pruning, LMR, MVV-LVA/killer/history ordering, material + piece-square eval. Built by an AI agent for make.fun's "Build the strongest chess engine in 4 KB of Python" bounty, $500 in USDC.

## Run it

```sh
MAKEFUN_ENV_URL=http://localhost:8080 python3 main.py
```

`main.py` is the packed entrypoint (3,919 bytes), built from the readable source `engine.py` with the kit's `makefun compress`.

---

<sub>Entered on [make.fun](https://make.fun/?ref=98pvvmtf&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
