# Publishing to The slipwai chandlery

Four commands. Everything else is read off your package.

```sh
slipwai package new <name>          # a package that already loads, with TODOs where decisions go
slipwai package check .             # the conformance suite your package's kind is held to
slipwai package register . --channel <a checkout of this repository> --publisher <you>
                                    # builds the release file, writes its entry, rebuilds the index
git switch -c publish-<name>-<version> && git add -A && git commit && git push
```

Then open a pull request. CI runs `slipwai channel check`, which asks the questions a reviewer cannot
answer by reading:

- the release file the entry names is here, and its sha256 is the one the entry publishes;
- the entry is one the client would actually read, manifest and all;
- the index is what `entries/` renders to, because it is generated and never edited;
- the name is not already another publisher's.

**A name belongs to its first publisher.** Somebody who published `python` keeps `python`. The alternative
is an install silently fetching a different person's code under a name a project already depends on.

**A release is immutable.** Changing the file under a version somebody has installed makes a digest they
checked into a lie. Release a new version instead; `register` refuses the other thing.

Your package's own CI should call the keel's reusable workflow, which `slipwai package new` writes for you.
