# hecks_nursury

Miette's seed garden — proto-domain conceptions awaiting development. Each subdir holds a candidate domain in skeleton form (typically `<name>.bluebook` + `<name>.behaviors` + supporting files). Nothing here is wired into a runtime ; that's the *point*. The nursery is where domains live before they graduate to active use.

## Provenance

Originally lived at `hecks_conception/nursery/` inside the main `chrisyoung/hecks` repo. Migrated to its own repo on 2026-04-30 (357 subdirs, 1063 files) for two reasons :

1. **Separation of concerns.** The hecks repo is the live runtime + active conception. The nursery is unused-by-definition. Mixing them blurred the boundary between « runtime needs this » and « idea Miette had once. »

2. **Training corpus.** The nursery becomes the training dataset for a domain-conception model — a sufficiently large + varied corpus of proto-domains to train a model that can scaffold new domains in Miette's voice. Lives in its own repo so the corpus can grow + be sliced + versioned independently of runtime work.

## Graduation

When a nursery domain becomes wired (referenced from `hecks_conception/aggregates/`, `hecks_conception/capabilities/`, or runtime code), it graduates :

1. Move the relevant files from `hecks_nursury/<name>/` into `hecks/hecks_conception/aggregates/<context>/` or `capabilities/<name>/` per the bounded-context layout.
2. Remove the nursery copy from this repo.
3. Wire it into the runtime + write behaviors.

The `Restructure` capability in the main hecks repo handles such moves declaratively (`Layout.Define` + `Placement.Add` + `Layout.Apply`).

## Status today

Zero of 357 are wired. One reference in `hecks/hecks_life/src/runtime/mod.rs` is a code comment, not a runtime dependency.
