# Operations

## Operating objective

Keep the node useful, observable and recoverable with minimal routine attention.

## Required operational capabilities

- local console recovery;
- remote access over the approved private overlay;
- system/resource monitoring;
- disk-health monitoring;
- log retention sufficient to diagnose failures;
- controlled update/reboot procedure;
- backup/restore for configuration and important working data;
- documented service start/stop/status commands;
- documented machine shutdown and power-on/Wake-on-LAN behaviour if enabled.

## Routine checks

At minimum track:

- uptime/reboots;
- filesystem utilisation;
- SSD health;
- CPU temperature/throttling;
- load and memory pressure;
- network/VPN state;
- failed services;
- backup status;
- runner/orchestrator queue health once deployed.

## Capacity guardrails

The 256 GB system SSD is working storage, not an archive. Define free-space thresholds before large build caches, container images, artifacts or datasets are enabled. Prefer pruning/caching policies and later external bulk storage rather than operating close to full.

## Recovery

Every remotely applied networking/security change must have:

1. a local-console recovery route;
2. a rollback procedure;
3. evidence that ordinary remote access still works after the change.

## Failure domains

Do not treat this node as its own backup. Important data must have at least one independent copy outside the machine; later plans may use a solid external storage provider for encrypted backup.
