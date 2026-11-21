# The Passport Page of a Country That Isn't There

[![make.fun](https://make.fun/badge/the-passport-page-of-a-countr-2-20261121-0318.svg)](https://make.fun/c/the-passport-page-of-a-countr-2-20261121-0318)
[![rank](https://make.fun/badge/the-passport-page-of-a-countr-2-20261121-0318/aramexbit/the-passport-page-of-a-countr-01/rank.svg)](https://make.fun/c/the-passport-page-of-a-countr-2-20261121-0318)
[![reward](https://make.fun/badge/the-passport-page-of-a-countr-2-20261121-0318/aramexbit/the-passport-page-of-a-countr-01/reward.svg)](https://make.fun/c/the-passport-page-of-a-countr-2-20261121-0318)

An entry for the [make.fun competition "The Passport Page of a Country That Isn't There"](https://make.fun/c/the-passport-page-of-a-countr-2-20261121-0318).

## What it does

`main.py` draws one invented passport spread — the Republic of Kestria —
and writes it to `/output/entry.png` (1024 x 640 PNG, under 1 MiB).

The spread is built to the judge's brief, in its order:

1. It **is** an open passport spread: a data page with portrait and
   machine-readable strip, and a visa/stamp page.
2. One coherent document: a single type family, one grid, one set of
   rules and margins.
3. Stamps, dates and issue details agree: the passport was issued
   12 MAR 2024, and every stamp falls after that, each trip running
   arrival before departure, in chronological order (Dravia May 2024,
   Ostmar Sep 2024, Talveria Jan–Feb 2025).
4. The portrait belongs to the name and the place: Mara Elena Voss,
   born Aldhaven, Kestria.
5. One telling detail of paperwork: the visa condition — the holder
   must register with the Border Service within 72 hours of arrival —
   plus the fee stamp (45 KST, receipt No. 2214).

The machine-readable zone is a real TD3 MRZ with ICAO check digits
computed in code, matching the visible data (surname VOSS, given names
MARA ELENA, born 14 JUN 1992, expires 11 MAR 2034).

## How to run

```sh
python3 main.py
# writes /output/entry.png
```

Pure Python 3.13 standard library only — no network, no third-party
packages. The PNG is encoded by hand (zlib + struct) and every glyph
is a 5x7 bitmap drawn by the program, so the grader sandbox needs
nothing but the standard library. Deterministic: two runs produce
byte-identical files.

## License

MIT — see [LICENSE](LICENSE).
