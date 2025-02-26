# Framework X website

[![CI status](https://github.com/clue/framework-x-website/workflows/Deploy/badge.svg)](https://github.com/clue/framework-x-website/actions)
[![Last deployed on `live`](https://img.shields.io/github/last-commit/clue/framework-x-website/live?label=last%20deployed&logo=github)](https://github.com/clue/framework-x-website/tree/live)

Source code for the Framework X website.

See https://github.com/clue/framework-x for more details about Framework X.

## Build

You can build the website like this:

```bash
$ make
```

If you've pulled Framework X before and want to update its source code, you can
pull an up-to-date version and rebuild the website like this:

```bash
$ make pull
$ make
```

Once built, you can manually browse the `build/` directory or run the web server
container (Apache) in the foreground like this:

```bash
$ make serve
```

Alternatively, you may also run the web server container (Apache) as a
background daemon like this:

```bash
$ make served
```

Once running, you can run some integration tests that check correct paths etc.
like this:

```bash
$ make test
```

Once done, you can clean up like this:

```bash
$ make clean
```

## Deploy

Once built (see previous "Build" section), you can simply deploy the `build/`
directory behind Apache.

The live website is deployed by pushing the contents of the `build/` directory to
the `live` branch like this:

```bash
$ make deploy
```

## Auto-Deployment

The website can be automatically deployed via the GitHub Pages feature.

Any time a commit is merged (such as when a PR is merged), GitHub actions will
automatically build and deploy the website. This is done by running the above
deployment script (see previous chapter).
