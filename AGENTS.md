# EDK II non-OSI (AIEN fork of tianocore/edk2-non-osi)

> Binary and non-OSI-licensed EDK II modules (firmware blobs, prebuilt drivers, per-module licenses) from TianoCore. AIEN keeps this copy because it is one of the four sources the Raspberry Pi 5 UEFI firmware in https://github.com/aien-dev/rpi5-uefi is built from. `master` matches upstream apart from a short AIEN note at the top of `Readme.md`; AIEN carries no code changes here.
Shared rules: read https://www.aienos.com/agents/RULES.md first. This file adds what is specific to this repository; where the two differ, this file wins here.

## Scope

- Applies to the whole repository. This is a fork, not an AIEN project.
- AIEN's own commit is exactly one: `ac81907` docs: README refresh for new readers (#1), which adds 4 lines (the fork note) to `Readme.md`. Every other commit is upstream history. `git diff <upstream master> HEAD` shows only `Readme.md`.
- Changes accepted here: AIEN documentation (the fork note at the top of `Readme.md`, this file) and fast-forward syncs from `tianocore/edk2-non-osi` `master`.
- Must not change: any file under `Drivers/`, `Emulator/`, `Platform/`, `Silicon/`, `Maintainers.txt`, any `License.txt`, or the upstream part of `Readme.md`. Do not add, rebuild or replace binaries.
- aien-dev/rpi5-uefi pins this repository at commit `1f4d784` as its `edk2-non-osi` submodule. That commit must stay reachable.

## Installation

```bash
git clone https://github.com/aien-dev/edk2-non-osi.git
cd edk2-non-osi
```

There is nothing to build or install. EDK II consumes this tree through `PACKAGES_PATH`; for the Raspberry Pi 5 build, `rpi5-uefi/build.sh` sets `PACKAGES_PATH=edk2:edk2-platforms:edk2-non-osi`.

## Usage

Check that the fork still differs from upstream only by the AIEN note:

```bash
git fetch https://github.com/tianocore/edk2-non-osi master
git diff --stat FETCH_HEAD HEAD          # expect: Readme.md only
git rev-list --count HEAD..FETCH_HEAD    # upstream commits not yet synced
```

Build and boot testing happen in aien-dev/rpi5-uefi, not here. That full TF-A + EDK2 build is slow and booting needs Raspberry Pi 5 hardware; do not run it for documentation changes.

## Conventions

- Licensing follows upstream `Readme.md`: there is no top-level License.txt; each module or group of modules carries its own `License.txt`, and the nearest one in the hierarchy wins.
- Keep the fork diffable against upstream: AIEN changes stay in the `Readme.md` fork note and this file.
- No em dashes or en dashes in AIEN-authored files.
- The repository has no CI workflows.

## Safety and approvals

- Ask before any change outside the accepted list in Scope.
- Never rewrite `master` history or force-push; rpi5-uefi and old builds reference these commits.
- Upstream fixes and new binaries go to tianocore/edk2-non-osi (see `Maintainers.txt`), not here.

## Further reading

- `Readme.md`: AIEN fork note, then the upstream README (licensing model).
- `Maintainers.txt`: upstream maintainers, mailing list and security reporting.
- https://github.com/aien-dev/rpi5-uefi and its `AIEN-NOTICE.md`: the firmware chain this copy belongs to.
- https://github.com/tianocore/edk2-non-osi: the original.
