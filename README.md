# WoW Addons Directory

A versioned directory of open-source World of Warcraft addons. Clients download one `addons.<flavor>.json` file per game flavor from this repository.

## Schema

Lists are validated against [`addons.schema.json`](addons.schema.json) (JSON Schema 2020-12).

Each flavor file is a complete catalog for that version. Addon entries do not repeat flavor; the file’s `flavor` field is the source of truth.

Supported flavors: `Retail`, `MoPClassic`, `Classic`, `BCAnniversary`, and `Forever`.

## Client downloads

Use GitHub raw URLs:

| Flavor | Path | Raw URL |
| --- | --- | --- |
| Retail | `addons.retail.json` | `https://raw.githubusercontent.com/bitobrian/wow-addons-directory/main/addons.retail.json` |
| MoP Classic | `addons.mop-classic.json` | `https://raw.githubusercontent.com/bitobrian/wow-addons-directory/main/addons.mop-classic.json` |
| WoW Classic | `addons.classic.json` | `https://raw.githubusercontent.com/bitobrian/wow-addons-directory/main/addons.classic.json` |
| BC Anniversary | `addons.bc-anniversary.json` | `https://raw.githubusercontent.com/bitobrian/wow-addons-directory/main/addons.bc-anniversary.json` |
| Forever | `addons.forever.json` | `https://raw.githubusercontent.com/bitobrian/wow-addons-directory/main/addons.forever.json` |

`Forever` is listed now so clients can subscribe early; the catalog stays empty until that version ships. Pin a commit SHA instead of `main` if the client needs an immutable snapshot.

Clients must use these root files. Do not download lists from `staging/`.

## Contributing

Propose addons by editing the copies in [`staging/`](staging/). A maintainer or agent reviews the linked source, then promotes approved entries into the published files above. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT. See [LICENSE](LICENSE).
