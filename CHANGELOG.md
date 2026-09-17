# Changelog

All notable changes to this fork are documented here.

This is a fork of [openwallet-foundation/askar](https://github.com/openwallet-foundation/askar),
diverged at `1eec2a1`.

### Changed

- **Breaking:** paginated fetches take an `offset`. `Session::fetch_all`,
  `Session::fetch_all_keys`, the `BackendSession` trait and both
  `askar_session_fetch_all*` FFI entry points gain the argument, and the SQLite
  and PostgreSQL backends pass it through instead of hard-coding `None`.
