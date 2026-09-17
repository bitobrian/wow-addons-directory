# WoW Addons Directory

A versioned directory of open-source World of Warcraft addons. Clients download one `<flavor>/<category>.json` file per game flavor and category from this repository.

## Schema

Lists are validated against [`addons.schema.json`](addons.schema.json) (JSON Schema 2020-12).

Each category file is the catalog for that flavor and category. Addon entries do not repeat flavor; the file’s `flavor` field is the source of truth. Category comes from the filename (and from each addon’s `category`, which must match that file).

Supported flavors: `Retail`, `MoPClassic`, `Classic`, `BCAnniversary`, and `Forever`.

## Client downloads

Use GitHub raw URLs:

`https://raw.githubusercontent.com/bitobrian/wow-addons-directory/main/<flavor>/<category>.json`

Flavor path slugs:

| Flavor | Path slug |
| --- | --- |
| Retail | `retail` |
| MoP Classic | `mop-classic` |
| WoW Classic | `classic` |
| BC Anniversary | `bc-anniversary` |
| Forever | `forever` |

Category path slugs:

| Category | Path slug |
| --- | --- |
| Bags | `bags` |
| Collections | `collections` |
| Combat | `combat` |
| Development | `dev` |
| Dungeons | `dungeons` |
| Economy | `economy` |
| Interface | `interface` |
| Quality of Life | `quality-of-life` |
| Quests | `quests` |
| Raiding | `raiding` |

Example: Retail quality-of-life → `https://raw.githubusercontent.com/bitobrian/wow-addons-directory/main/retail/quality-of-life.json`.

`Forever` folders exist so clients can subscribe early; they stay empty until that version ships. Pin a commit SHA instead of `main` if the client needs an immutable snapshot.

Clients must use these root flavor folders on `main`. Do not download lists from the `staging` branch.

## Contributing

Propose addons by opening a pull request against the `staging` branch. A maintainer or agent reviews the linked source, then publishes by merging `staging` into `main`. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT. See [LICENSE](LICENSE).
