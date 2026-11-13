# ssh-agent-lib, mark-ik fork

A patch-only fork of [wiktor-k/ssh-agent-lib](https://github.com/wiktor-k/ssh-agent-lib)
for the Mere family's one-version plan (engine-split D144; Mark, 2026-11-13:
"Fork ssh-agent-lib now"). The family moves to `ssh-key` 0.7, and the latest
ssh-agent-lib release (0.6.0) still requires `ssh-key` 0.6, `signature` 2 and
`ssh-encoding` 0.2, which would keep two generations of the RustCrypto SSH and
signature crates in every family graph.

- **Base:** upstream tag `v0.6.0` (`59707d160628ca4804a7e21cf4e8a5cdc59f2e02`),
  the commit the published 0.6.0 crate was built from (its `.cargo_vcs_info.json`).
- **Crate name and version:** unchanged (`ssh-agent-lib` 0.6.0). Consumers name
  this repository by git, `branch = "main"`, `version = "0.6"`.
- **Licence:** unchanged, MIT OR Apache-2.0; `LICENSE-MIT` and `LICENSE-APACHE`
  are identical to the published 0.6.0 crate's.
- **Rules:** dependency moves and the call adaptations they force, nothing else:
  no new features, no protocol, key-handling or encoding logic of our own.
  Where upstream's unmerged branch `baloo/push-opnrsxswnwos` (Arthur Gautier,
  2026-05-20, on `ssh-key` 0.7.0-pre.1) already made a change, its shape is used.

## Patches

| Commit | Change |
|---|---|
| 8599cbe | Move to `ssh-key` 0.7.0-rc.12, `ssh-encoding` 0.3 and `signature` 3; dev-dependencies to rand 0.10, rsa 0.10, sha1 0.11, sha2 0.11 and p256 0.14. |

The test suite is the same before and after: 6 + 21 + 8 tests, all passing,
including the protocol round-trip fixtures, so no message byte changed.

## Retirement

This fork retires when upstream releases ssh-agent-lib on `ssh-key` 0.7: the
family's rows go back to the registry release and this repository is archived.
`LEDGER.md` records what we found for upstream; Mark reads it and decides what
to post.
