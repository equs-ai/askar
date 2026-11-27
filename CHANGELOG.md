# Changelog

All notable changes to this fork are documented here.

This is a fork of [openwallet-foundation/askar](https://github.com/openwallet-foundation/askar),
diverged at `1eec2a1`.

### Changed

- **Breaking:** paginated fetches take an `offset`. `Session::fetch_all`,
  `Session::fetch_all_keys`, the `BackendSession` trait and both
  `askar_session_fetch_all*` FFI entry points gain the argument, and the SQLite
  and PostgreSQL backends pass it through instead of hard-coding `None`.
- Published as `equs-aries-askar`, `equs-askar-crypto` and `equs-askar-storage`,
  since all three names are taken on crates.io by upstream. Each keeps its old
  `[lib]` name, so imports are unchanged.
- `equs-askar-storage` uses sqlx 0.9 (upstream `4e35af1`), which takes
  `libsqlite3-sys` 0.40 and clears RUSTSEC-2026-0459. `equs-aries-askar` and
  `equs-askar-storage` need Rust 1.94.
