# Upstream ledger

Findings worth raising with wiktor-k/ssh-agent-lib. Nothing here has been posted;
Mark reads and posts.

## 2026-11-13: no release on the ssh-key 0.7 line

- Latest release 0.6.0 (2026-05-21) requires `ssh-key ^0.6`, `signature ^2`,
  `ssh-encoding ^0.2`; upstream `main` (3114e4e, 2026-09-15) still does.
- The branch `baloo/push-opnrsxswnwos` (2026-05-20) ports to `ssh-key`
  0.7.0-pre.1 and was never merged. Its code changes apply to v0.6.0 with one
  conflict (the `pubkey` field became `credential` in 0.6.0) and still build
  against `ssh-key` 0.7.0-rc.12.
- On rc.12 and the released rsa 0.10.0 two more changes are needed in the
  examples only: rsa 0.10 no longer has `sha1`/`sha2` features or re-exports
  `rsa::sha2`, so the examples import `sha2` directly; and `rsa::RsaPrivateKey`
  is deprecated in favour of `rsa::PrivateKey` (left as a warning here).
- The library's own tests (6 + 21 + 8) pass unchanged on the new line.
