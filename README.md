# P car research

Living market notes for a $60,000 search: a Porsche 911 Carrera S or above, or a six-cylinder Cayman.

Each pass is a dated snapshot. The latest one is [4 October 2026](reports/2026-10-04-60k-market.md). The shopping medians are in [data/2026-10-04-cars-and-bids.json](data/2026-10-04-cars-and-bids.json). The wider 911 and Cayman ladder from the same day is in [data/2026-10-04-lineup-additions.json](data/2026-10-04-lineup-additions.json).

A local copy of this repo lives at `Documents\p-car-research`. The interactive view of the latest snapshot is the Cursor canvas `porsche-60k-market.canvas.tsx`.

## Search rules

- Budget: $60,000 for the winning bid plus the Cars & Bids buyer fee. Tax, title, and shipping are extra.
- Buyer fee used here: 5% of the hammer, minimum $250, maximum $7,500. That puts the bid ceiling at about $57,100.
- 911: Carrera S and above. That includes S, 4S, GTS, Targa 4S, Turbo, and GT cars. A base Carrera, Carrera 4, or Carrera T is out.
- Cayman: six-cylinder only. Every 987 and 981 qualifies. A 718 qualifies only as a GT4, GT4 RS, or GTS 4.0. The 718 base, S, T, and original GTS are flat-4s.

## How the next update works

Add a new snapshot. Leave older files in place so the history stays readable.

1. Pull sold and live results for the cars above.
2. Save `data/YYYY-MM-DD-<source>.json` using the same fields as `data/2026-10-04-cars-and-bids.json` (`snapshot_date`, `source`, `buckets`, `live`, `auctions`).
3. Write `reports/YYYY-MM-DD-60k-market.md` with the recommendation, the medians, and what changed since the previous report.
4. Point the "latest" link at the top of this file at the new report.
5. Refresh the Cursor canvas from the new snapshot.

## Sources

In use:

- [Cars & Bids Porsche search](https://carsandbids.com/search/porsche), first snapshot 4 October 2026.

Planned, so a later pass can add them without changing the question:

- Bring a Trailer, for a second sold-price set
- Dealer and classified asking prices (Autotrader, Cars.com, Porsche finder)
- PCA Mart, for private-party asking prices

Asking prices and sold prices stay in separate files. A listing that has not sold is not a comp.
