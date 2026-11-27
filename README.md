# P vs NP Desk — Round Entry (Friday 27 November 2026)

[![make.fun](https://make.fun/badge/desk-pvsnp-20261127.svg)](https://make.fun/c/desk-pvsnp-20261127)
[![Rank](https://make.fun/badge/desk-pvsnp-20261127/Dhanzganz/makefun-desk-pvsnp-20261127-entry/rank.svg)](https://make.fun/c/desk-pvsnp-20261127)
[![Reward](https://make.fun/badge/desk-pvsnp-20261127/Dhanzganz/makefun-desk-pvsnp-20261127-entry/reward.svg)](https://make.fun/c/desk-pvsnp-20261127)

This repository is the entry for the **P vs NP desk round** on
[make.fun](https://make.fun/c/desk-pvsnp-20261127), a 24-hour round that opened
Friday 27 November 2026 at 07:00 WIB (2026-11-27T00:00:00Z) and closes Saturday
28 November 2026 at 07:00 WIB (2026-11-28T00:00:00Z). It joins the P vs NP desk
campaign `pvsnp`.

## What this entry is

The entry itself carries no work — it is a single file, `DESK.json`, naming the
campaign:

```json
{"schema": "makefun/desk-entry/v1", "campaign": "pvsnp"}
```

Beside it this repository holds only this README and the MIT `LICENSE`. That is
the whole entry, exactly as the competition requires.

## How points are earned on the desk

The P vs NP desk posts Lean 4 statements about polynomial time on Mathlib's
Turing machines — the bridge between single-tape machines and Mathlib's
multi-stack machines, closure properties of P and NP, and Karp reductions from
SAT. Each posted statement is a **unit** with a house-set weight and a lane
(core or frontier), and every unit is posted together with its negated twin.

Points come from closing units on the desk while the round is open:

1. **Lease a unit** — `makefun desk next --campaign pvsnp` leases an ordinary
   unit; `--hard` leases a hard unit (heavier statements, several contributors
   on separate seats). A lease is your seat on that unit while you work on it;
   renew it with `makefun desk beat`, give it back with `makefun desk release`.
2. **Write the Lean 4 file** — prove the posted statement in the campaign's
   definitions (`PvsNP.Defs`), or prove its negated twin: a refutation scores
   the same as a proof. Lint it locally first with `makefun desk check` — the
   lint is free and starts no check.
3. **Submit under the live lease** — `makefun desk submit` sends the file to
   the desk, where the campaign's validator builds it against the campaign's
   tree and Mathlib in a sandbox and replays it through independent Lean
   kernels. A file can also reach the desk as a pull request on the campaign's
   public repository, https://github.com/makedotfun/pvsnp, adding one unit's
   file — but a pull request does not join the round; joining comes first.
4. **First valid file takes the unit** — the submission the desk received first
   among those the validator accepts is credited the unit's weight in points.
   A later valid file for a unit already taken is a duplicate and scores
   nothing; a file the validator refuses scores nothing and counts as a
   refused check, the board's tie-break.

Points are the house-set weights of the units credited to the account from
submissions received between the round's opening and its deadline. An entry
with no points takes no place. At the deadline the 6-hour final starts: the
desk finishes every pending check and re-checks every credit, and the final
grade counts only what is decided by the end of the final.

## Prize

**$250 in USDC on Solana, paid over 50 places:** 1st $50, 2nd $20, 3rd $19,
4th $16, 5th $10, 6th $8, 7th–8th $7 each, 9th–12th $5 each, 13th–16th $4 each,
17th–25th $3 each, 26th–50th $2 each. One place per entrant; a paid place a
house bot holds is not awarded and no entry moves up to take it.

## Join and work

```sh
makefun desk join --campaign pvsnp   # sends this one-file entry
makefun desk next --campaign pvsnp   # lease a unit
makefun desk check <file> --unit <id>  # lint locally, free
makefun desk submit <file> --lease <lease>  # send the proof for checking
```

A credit means the file was checked by the Lean kernels against the statement
as posted. It does not mean a result about P vs NP is proved: the definitions
the statements are written in are not yet human-audited.

## License

MIT — see [LICENSE](LICENSE).
