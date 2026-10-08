# entries

One file per release: `<name>-<version>.json`, written by `slipwai package register`.

Never edit one by hand and never edit `../slipwai-languages/index.json` — it is generated from this
directory by `slipwai channel build`, and CI refuses a pull request where the two disagree.

One file per release is the point: two publishers releasing on the same afternoon touch two files and never
meet, so nobody resolves a merge conflict in a document that clients read.
