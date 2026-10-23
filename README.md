# Docs Sync

A Camillia camflow that runs after an implementation: it reads the code change on the
task branch, compares it with the documentation tree, and proposes the matching
documentation updates — stale pages corrected, incomplete pages completed, gaps filled.

## What it does

1. **Collects the change** — diffs the task branch against its base and builds an
   evidence-cited inventory of everything a user, administrator, or integrator can
   observe: behavior, configuration, data/migrations, interfaces.
2. **Audits the docs** — maps the README/docs tree and classifies every affected page
   as stale, incomplete, missing, or fine, checking the usual traps (config tables,
   defaults, CLI help copies, screenshots, API references, tutorials).
3. **Applies the updates** — minimal, style-matching edits via patch; stale workspace
   knowledge corrected in place; assets that need re-capture are flagged, not faked.
4. **Decides and finishes** — commits the docs updates and moves the task to review
   only when every inventory entry is documented or deliberately deferred with a reason.

## How it triggers

Task-type camflow. Schedule it on the task whose implementation just landed (for
example right after an implementation task reaches review), or bind it to a task event
in your workspace trigger bindings.

## Install

Install from the Camillia Community Hub. The hub imports `camflow.yaml` into your
Camillia instance; no other files are required at runtime.

## License

MIT — Copyright (c) 2026 Camillia contributors. See [LICENSE](LICENSE).
