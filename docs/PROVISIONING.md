# Provisioning policy

## Goal

Turn successful manual setup into a reproducible host configuration without erasing the machine's original state before it is understood.

## Sequence

1. Inventory existing machine and preserve recovery material.
2. Decide operating system from measured requirements and hardware support.
3. Install with a minimal package set and known partitioning.
4. Establish secure administration and time/DNS/update behaviour.
5. Install development toolchains and monitoring.
6. Add VPN and private service bindings.
7. Add repository/build tooling.
8. Convert repeatable configuration into scripts/config files.

## Desired properties

- bootstrap scripts are idempotent or clearly state when they are not;
- package/tool versions are recorded;
- machine-specific secrets are injected outside Git;
- configuration has a dry-run or inspection path where practical;
- scripts fail closed rather than silently skipping security-critical steps;
- changes are small enough to diagnose independently.

## OS decision

No distribution is yet canonical. Selection should consider:

- driver support for the Quadro M620;
- long-term security maintenance;
- compatibility with Cybersand/Godot/native toolchains;
- self-hosted CI tooling;
- WireGuard and monitoring support;
- low idle overhead;
- unattended/headless operation.

Record the chosen OS and rationale in `DECISIONS.md` before making it authoritative.
