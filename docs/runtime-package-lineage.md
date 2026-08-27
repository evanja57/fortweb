# Runtime package lineage

FortWeb adapted selected ideas from three pull requests by Jay-Alexander Elliot. The implementation was written in this branch. No donor commit was cherry-picked.

| Donor | Frozen donor commit | Adapted behavior |
| --- | --- | --- |
| [PR #27](https://github.com/keri-foundation/fortweb/pull/27) | [`e079701a337468acb1484a1c2cf86acc517d8464`](https://github.com/keri-foundation/fortweb/commit/e079701a337468acb1484a1c2cf86acc517d8464) | Runtime package contract, release metadata, package manifest and verifier structure, local server guidance, copy icon, and modular worker behavior. |
| [PR #32](https://github.com/keri-foundation/fortweb/pull/32) | [`2d7c0883798a75b074407a3e205391c7e4195ba2`](https://github.com/keri-foundation/fortweb/commit/2d7c0883798a75b074407a3e205391c7e4195ba2) | Empty-state, route, sidebar, runtime-origin, and browser-noise test cases. |
| [PR #35](https://github.com/keri-foundation/fortweb/pull/35) | [`b179e868c997d29479a61ecec8ad5834a00d1578`](https://github.com/keri-foundation/fortweb/commit/b179e868c997d29479a61ecec8ad5834a00d1578) | Pyodide boot canary, runtime configuration, and browser integration test structure. |

Jay-Alexander Elliot authored the donor commits. His recorded commit email is `alexander.elliot.it@protonmail.com`.

## Adaptation boundary

FortWeb keeps the donor concepts only where they match the Pyodide 314 runtime design. It replaces the legacy Pyodide 0.29.3 and CPython 3.13 package set, old `hio_web` and `keri_web` wheels, `pychloride`, absolute runtime paths, the monolithic worker, hard-coded origin data, and drawer-only readiness checks.

The committed source boundary includes the runtime package schema and reusable manifest, metadata, deterministic ZIP, and verifier primitives. The acceptance-only package orchestrator stays in private execution state because it is bound to the previous source identity and consumer snapshots. A later source change must rebuild the runtime and package before any extracted-package or consumer claim is valid.

The eventual pull request description must retain this attribution and the no-cherry-pick statement.
