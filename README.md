# copalibre-modules

The curated repository of community-authored [CopaLibre](https://github.com/SebaSOFT/copalibre)
disciplines and tournament profiles. `copalibre module add <alias>[@range]` resolves and installs
from here by default — an operator never needs to know a module's location, only its name.

Modules are data, never code: a discipline or profile is a JSON document referencing a fixed,
core-owned vocabulary of rule actions/conditions/parameters. Nothing published here can execute
arbitrary logic on an installation.

## Repository layout

```
disciplines/<alias>/
  manifest.json   — kind, alias, version, attribution, requiresCopalibre, declared assets
  artifact.json   — the discipline descriptor document
  assets/         — optional background/logo images, only what manifest.json declares
profiles/<alias>/
  manifest.json
  artifact.json   — the tournament profile document
  assets/
```

See `disciplines/orbital-frisbee/` and `profiles/weekend-cup/` for worked, minimal examples of
each kind.

## Contributing a module

1. Fork this repository.
2. Add your module under `disciplines/<your-alias>/` or `profiles/<your-alias>/`, following the
   layout above. Pick an alias nobody else has used here — the same alias can never mean two
   different things across installations.
3. Open a pull request. The `Validate modules` check runs the identical validation
   `copalibre module add` runs at install time: manifest and artifact schema, every referenced
   action/condition/parameter against the published core registry, a real ruleset-compilation
   pass, asset format/dimension/size limits, and — this is the check that actually protects the
   namespace — a refusal if your alias collides with one the first-party catalogue already ships.
   A failing check names exactly what to fix.
4. Once merged, publish the version by pushing a tag named `<alias>@<version>` (semver) pointing
   at the merge commit — `copalibre module add <alias>` resolves the highest published tag
   satisfying the requested range, so nothing is installable until its tag exists.

### Versioning and updates

Each new `artifact.json` revision is a new `version` in `manifest.json`, tagged separately
(`<alias>@<new-version>`) — never overwrite a published tag. `attribution` must stay the same
author/licence across every version of your alias; changing it reads as a different author trying
to claim the name, which the CLI refuses on install.

## When not to publish here

An internal discipline a federation will never publish, or a module for an air-gapped
installation, doesn't belong in a public repository at all. `copalibre module add` supports an
explicit `--source <url>` flag against any Git repository an operator has allow-listed locally
(`COPALIBRE_MODULE_SOURCE_ALLOWLIST` in their installation's environment) — see
[`docs/deployment/community-modules.md`](https://github.com/SebaSOFT/copalibre/blob/develop/docs/deployment/community-modules.md)
in the core repository for the full private-source path. That path runs the identical validation
this repository's pull requests do; it is never a way to skip it.

## License

The tooling and documentation in this repository are MIT licensed (see `LICENSE`). Each module's
own content carries its own licence, declared in its `manifest.json`/`artifact.json`
`attribution.licence` field.
