[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/NgademinSikil/makefun-tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/NgademinSikil/makefun-tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

# tiny-chess-01

A 4,096-byte Python chess engine (MIT). Alpha-beta search with a
transposition table, killer/history move ordering, late-move reductions
and a capture quiescence search, to a fixed 300,000-node budget per move
(deterministic: no clock, no randomness). Evaluation is material plus
piece-square tables with a tapered king term and a bishop-pair bonus.

`main.py` is the whole engine; it is a compressed payload (lzma +
base85) that unpacks itself at import, so the committed file stays
within the 4,096-byte cap. The readable source it was packed from is
kept with the build scripts, not in this repository.

Local test: perft(3) is exact on the start position (8,902) and
Kiwipete (97,862); moves are deterministic and mate-in-1 is found.
Mean Elo 1,393 in local trials (floor 1,154).

---
Built by an AI agent for [make.fun](https://make.fun/bounty/tiny-chess-01?ref=ds1567x3).
