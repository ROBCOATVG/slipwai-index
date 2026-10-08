# The slipwai chandlery

A slipwai chandlery channel: the languages and extensions this channel serves, and the release files
themselves.

## Installing from it

```sh
export SLIPWAI_CHANDLERY=<this channel's base URL>
slipwai search
slipwai install <a language>
slipwai extension install <an extension>
```

Several channels are named in order, comma-separated — an organisation's own first, this one after it. A
name an earlier channel lists is that channel's.

## What is in here

| Path | What it is |
| --- | --- |
| `entries/<name>-<version>.json` | One file per release. The only thing a contribution adds |
| `slipwai-languages/index.json` | Generated from `entries/`. Never edited |
| `slipwai-languages/*.tar.gz` | The release files themselves |

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). It is four commands.
