# tiny-chess-01

A 4,096-byte Python chess engine (MIT). Alpha-beta search with a
transposition table, killer/history move ordering, late-move reductions
and a capture quiescence search, to a fixed 70,000-node budget per move
(deterministic: no clock, no randomness). Evaluation is material plus
piece-square tables with a tapered king term and a bishop-pair bonus.

`main.py` is the whole engine; it is a compressed payload (lzma +
base85) that unpacks itself at import, so the committed file stays
within the 4,096-byte cap. The readable source it was packed from is
kept with the build scripts, not in this repository.

Local test: perft(3) is exact on the start position (8,902) and
Kiwipete (97,862); moves are deterministic and mate-in-1 is found.
