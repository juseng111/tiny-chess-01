# BUILD.md — tiny-chess-01

Engine: `engine.py` (10,568 bytes readable), packed with the kit's
`makefun compress` into `main.py` (3,919 bytes, <= 4,096).

## Design

0x88 board, signed-int pieces, piece lists, incremental material +
piece-square score, Zobrist hash (fixed seed). Search: alpha-beta,
iterative deepening to a fixed 60,000 nodes/move (never a clock), max
depth 12, transposition table (cleared between games), killer + history
ordering, MVV-LVA captures, null-move pruning (R=2), late-move reductions,
quiescence (captures + promotions, full evasions in check). Eval: material
P=100 N=320 B=330 R=500 Q=1000, middlegame tables, endgame king table
blended by phase, tempo +10. Deterministic: fixed node budget, fixed-seed
Zobrist, no wall clock, no unseeded randomness.

## Tests (all pass)

- Perft vs python-chess (test-only reference, never part of the entry):
  6 standard positions, depths 1-4, 20 checks, **0 fails** (startpos d4
  197,281; Kiwipete d3 97,862; position 3 d4 43,238).
- Eval sanity: startpos eval 10 (tempo), score 0; after 1.e4 score 40.
- Mate-in-1: Qxf7 found. Determinism: same position -> same move.
- Speed: worst move 0.98 s at 60,000 nodes (sharp middlegame), 55-99k
  nps; well under the 10 s/move env limit.
- Practice trial (local env server, trial-0, packed `main.py`): see below.

## Practice trials

Packed `main.py` vs the kit's local env server, scored with the kit's
scorer: trial-0 Elo 1545 (3W 3D 0L), trial-1 Elo 1364 (2W 3D 1L),
trial-2 Elo 1545 (3W 3D 0L). Mean 1485; 8W 9D 1L in 18 games. Practice
floor 1154; sunfish house baseline ~1325 mean. Above both.

## License

MIT, SPDX-License-Identifier: MIT (first line of LICENSE).
