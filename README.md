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

A release file lives on the tag that built it, not here: git keeps every version of every file for ever,
and a channel holding its own tarballs grows without bound. An entry names the URL and the digest, and the
digest is what makes somebody else's URL safe to list — a publisher who replaces the file afterwards has
broken their own package, because the client refuses bytes that are not the bytes the index named.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). It is four commands.

## Which keel checks this

CI installs `slipwai` from PyPI and runs `slipwai channel check .` — the keel's own code, not this
repository's, because a channel that checks itself is only as good as that channel.

To check against a keel that is not on PyPI yet, set a repository variable:

```sh
gh variable set SLIPWAI_KEEL -R <owner>/<repo> --body 'git+https://github.com/ROBCOATVG/slipwai@main'
```

Unset it once the version you need is published.
