# Geladeiras no Brasil — Data Repository

Canonical fridge dataset for the Brazilian market. 109 models, April 2026 pricing.

**Frontend:** [br-fridges-web](https://github.com/HugoJF/br-fridges-web) → [hugojf.github.io/br-fridges-web](https://hugojf.github.io/br-fridges-web/)

## Data

**`fridges.json`** — machine-readable array of all models. Fetch via raw URL:

```
https://raw.githubusercontent.com/HugoJF/br-fridges/main/fridges.json
```

Schema defined in `fridge-types.ts`. Each entry:

- `id` — slug (e.g. `consul-cra30fb`)
- `brand`, `model`
- `capacity` (liters)
- `type` — `compact` | `top-freezer` | `bottom-freezer` | `side-by-side` | `french-door`
- `width`, `height`, `depth` (cm); `depthWithDoors` (cm, nullable)
- `reversibleDoors` (boolean | null)
- `inverterCompressor` (boolean | null)
- `monthlyKwh` (nullable — from INMETRO/PBE where available)
- `price` (approximate BRL)

## Source notes

`models/` — per-model research notes with sourcing details.

## Data & accuracy

Prices and specs were gathered from retailer listings and manufacturer pages. They reflect availability at the time of research and may be outdated. Use as a starting point for comparison, not as a purchase guarantee.

Monthly power consumption is sourced from official INMETRO / PBE data when a reliable current match exists. The fetch/match process is documented in [INMETRO_PBE.md](INMETRO_PBE.md).

## Contributing

Pull requests welcome — especially corrections to specs or prices, and new models. Keep the data format consistent with the existing entries in `index.html`.

## License

[MIT](LICENSE)
