# Evidence policy

## Purpose

Every implementation issue should leave enough evidence for a later agent to determine what happened without relying on chat memory.

## Minimum evidence per issue

- exact commands or script entry points used;
- relevant tool/package versions;
- machine state before and after when the change is material;
- raw logs or machine-readable results where useful;
- concise Markdown interpretation;
- failures/anomalies, including failed approaches;
- rollback/recovery notes for configuration changes;
- final verification result against the issue acceptance criteria.

## Suggested paths

```text
evidence/
  inventory/
  health/
  benchmarks/
  network/
  security/
  provisioning/
  workloads/
  operations/
```

Large generated artifacts should not be committed blindly. Store summaries, checksums and retrieval locations if raw data is too large for ordinary Git.

## Measurement metadata

Benchmark evidence should include timestamp, OS/kernel, firmware where relevant, CPU governor/power mode, temperatures, free disk space, background-load notes, benchmark/tool version and repeated-run statistics.

## Security evidence

Never capture private keys, passwords, tokens, recovery codes or other secrets in logs committed to the repository. Redact before publication and prefer commands that do not echo secrets.
