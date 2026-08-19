# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- GitHub issue templates: bug report, feature request, and a security
  report template that directs reporters to `SECURITY.md` instead of
  accepting inline disclosures.
- Pull request template with a checklist matching the expectations in
  `CONTRIBUTING.md` (`make check` passes, tests added or updated,
  `CHANGELOG.md` updated).
- `SECURITY.md` security policy with a private reporting channel.
- `attester-registry`: `update_attester_info`, an admin-authorized entry
  point for changing an already-allowlisted attester's metadata without
  re-enrolling it. Emits `AttesterInfoUpdated`, which is distinguishable
  from `AttesterAdded`, and fails with the new `Error::AttesterNotFound`
  when the attester is not currently allowlisted (never added, or since
  removed).
- `attester-registry`: `get_attester_status`, a combined read returning an
  attester's metadata together with its current suspension state in one
  call.
