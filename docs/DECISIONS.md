# Decision log

Use this file for programme-level choices that later agents must not silently reverse.

## D-001 — Start with one known-good i7-6700 node

**Status:** accepted.

The i7-6700 / 16 GB / 256 GB SSD / Quadro M620 machine known to work is the sole implementation target for the initial programme. The second similar machine is deferred until separate hardware inspection determines whether its exposed package is safe.

## D-002 — Prefer physical network isolation

**Status:** accepted direction, infrastructure not yet commissioned.

The automation environment should ultimately use a separate FTTP connection/router/LAN from the household network. Do not compensate for convenience by creating routes back into the household LAN.

## D-003 — Use a private overlay for administration

**Status:** accepted direction.

WireGuard or an equivalently lightweight private overlay is preferred for administration and agent-to-agent communications. Application authentication remains required.

## D-004 — Baseline before tuning

**Status:** accepted.

Do not change cooling, power limits, storage, GPU, OS configuration or performance tuning merely to improve benchmark scores before the initial evidence baseline is captured.

## Deferred decisions

- canonical operating system/distribution;
- whether the node becomes a self-hosted GitHub runner;
- whether a permanent external VPS is required;
- external backup provider and retention policy;
- bulk/seedbox storage integration;
- Wake-on-LAN/power scheduling;
- role of the Quadro M620 beyond display/basic compatibility testing.

Resolve each deferred decision through an issue that records evidence and rationale here.
