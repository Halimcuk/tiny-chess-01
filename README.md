# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Halimcuk/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Halimcuk/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in 4 KB of Python, written from scratch for make.fun's
"Build the strongest chess engine in 4 KB of Python" bounty ($500).

## Engine

`main.py` is the whole engine: a 0x88 board, negamax with alpha-beta and
principal-variation search, piece-square evaluation, quiescence search
with delta pruning, MVV-LVA + killer + history move ordering, a
transposition table, null-move pruning, and iterative deepening to a
fixed node budget per move. Deterministic: no clock, no randomness, so a
replay plays the same moves. It talks to the trial env at
`MAKEFUN_ENV_URL` (`POST /game`, `POST /move`) and plays the 8-game
house gauntlet. No model calls, standard library only.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

## Build

`main.py` is the kit's `makefun compress` packing of `src/engine.py`
(the readable source, kept beside the entry, not committed). Rebuild
after any change with:

```sh
node cli/makefun.mjs compress src/engine.py --out main.py
```

Referral code: `jcrs26fr`

---

<sub>Entered on [make.fun](https://make.fun/?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
