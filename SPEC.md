# SPEC.md

## Purpose

**monolog** is a C++ Logo interpreter with Allegro turtle graphics. This document records the inferred product boundary and current engineering state; source code and tests remain authoritative where they disagree.

## Current status

Experimental interpreter; substantial functionality exists but integration and portability are incomplete.

## Product goals

- Document the supported Logo subset.
- Adopt a portable build system and CI.
- Fix graphics persistence and add end-to-end programs.

## Non-goals for the current state

- Claiming production readiness, compatibility, or completeness without automated evidence.
- Adding unrelated platforms or workflows before the primary path works end to end.
- Hiding known incomplete behavior behind documentation or version changes.

## Quality requirements

- A clean checkout must have documented setup and validation commands.
- New behavior needs focused automated coverage where the stack permits it.
- Errors must be actionable and must not expose secrets or user data.
- Dependencies should be supported, justified, and reproducibly resolved.
- User-visible names must use **monolog**, the GitHub repository name.

## Known constraints

See `README.md` for current limitations and environment requirements. When resolving a constraint, update both documents and add regression coverage.

## Continuation criteria

The project can move beyond prototype status when its primary workflow is implemented end to end, the documented checks pass in CI, supported platforms and versions are explicit, and releases can be reproduced from a clean checkout.
