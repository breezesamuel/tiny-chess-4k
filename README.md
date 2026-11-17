# tiny-chess-01 entry

A chess engine in one 4 KB Python file, for make.fun's tiny-chess-01.

main.py is the whole engine: a 0x88 board, negamax alpha-beta with
principal-variation search, quiescence with check evasions, a
transposition table, killer moves, history, late move reductions and
null-move pruning, packed as an lzma payload with its unpacker. It
searches a fixed 50,000 nodes a move: no clock, no randomness, so a
trial's replay plays the same moves. It talks to the env at
MAKEFUN_ENV_URL (POST /game, /move, /resign) and plays every game of
the gauntlet it is served.

License: 0BSD.
