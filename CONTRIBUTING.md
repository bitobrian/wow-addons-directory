# Contributing

Anyone can propose an addon. Proposals are pull requests into **`staging`**. The `main` branch is the published catalog; only maintainers merge `staging` into `main` after review. `main` is protected.

## Why a `staging` branch?

Clients fetch `main`. Merging a PR straight into `main` would publish before source review. `staging` is the same tree, not a client URL. Pending approved listings can sit on `staging` until a maintainer publishes.

## Propose an addon

1. Fork this repository.
2. Branch from `staging`.
3. Edit `<flavor>/<category>.json` (example `retail/quality-of-life.json`). Append an object that matches [`addons.schema.json`](addons.schema.json). Use a unique kebab-case `id`.
4. Open a pull request **into `staging`**, not `main`.

If the addon supports several flavors, add the same object to each matching flavor’s **same category** file.

## What reviewers do

1. Confirm the PR targets `staging`.
2. Clone `https://{host}/{owner}/{repo}` at a pinned commit.
3. Scan that source for safety problems (unexpected network calls, obfuscated code, credential collection, automation that would break Blizzard’s terms, and similar).
4. Check that `id`, `name`, `summary`, `category`, and tags match the project.
5. If approved, merge into `staging`. Rejected proposals are not merged; close the PR.
6. Publish when ready: open a pull request from `staging` into `main` and merge it. Do not push commits directly to `main`.

## Clients

Always download `main` (see the [README](README.md) for raw URLs), never the `staging` branch.
