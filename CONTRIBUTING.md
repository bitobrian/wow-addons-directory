# Contributing

Anyone can propose an addon. Proposals go into **`staging/`**. The JSON files at the repository root are the published catalog; only maintainers copy entries there after review.

## Why `staging`?

The published files are what clients fetch from GitHub. If a PR wrote straight to those files, a merged listing would go live before anyone inspected the addon source.

`staging` is a holding area: same schema, same filenames, not a client URL. Other names we considered (`inbox`, `proposed`, `review-queue`) mean the same thing. `preprocessing` sounds like a build step, so we avoided it.

## Propose an addon

1. Fork this repository.
2. Edit only the flavor file(s) under `staging/` (for example `staging/addons.retail.json`).
3. Append an object that matches [`addons.schema.json`](addons.schema.json). Use a unique `id` (`kebab-case`).
4. Open a pull request that **does not** change the root `addons.*.json` files.

If the addon supports several flavors, add the same entry to each matching staging file.

## What reviewers do

1. Confirm the PR only touches `staging/` (plus docs if needed).
2. Clone `https://{host}/{owner}/{repo}` at a pinned commit.
3. Scan that source for safety problems (unexpected network calls, obfuscated code, credential collection, automation that would break Blizzard’s terms, and similar).
4. Check that `id`, `name`, `summary`, `category`, and tags match the project.
5. If approved, copy the addon object into the root `addons.<flavor>.json` for each accepted flavor. Keep `staging/` in sync so it remains a superset of published listings plus anything still pending.

Rejected proposals stay out of the root files. The staging PR can be closed or the entry removed.

## Clients

Always download the root files, never `staging/`. See the [README](README.md) for raw URLs.
