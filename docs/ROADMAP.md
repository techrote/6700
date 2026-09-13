# Roadmap

## Phase 0 — programme intake

- establish repository authority and RAG pack;
- capture current photographs/labels if useful;
- inventory the known-good machine without destructive change;
- preserve recovery/licence/data state.

## Phase 1 — hardware qualification

- inspect SSD SMART/health;
- memory test;
- thermals/clocks/power baseline;
- CPU/memory/storage/network benchmark suite;
- establish repeated-run variance envelope.

## Phase 2 — OS and reproducible provisioning

- select canonical OS from explicit requirements;
- install/reconfigure only after recovery evidence exists;
- establish bootstrap scripts/configuration;
- monitoring, logging and capacity guardrails.

## Phase 3 — secure automation networking

- prepare WireGuard/private-overlay model;
- harden host firewall and service bindings;
- validate remote recovery path;
- later migrate onto the physically separate FTTP/LAN when available;
- prove there is no route into the household LAN.

## Phase 4 — development workload qualification

- install native/Godot/Cybersand-relevant toolchains as required;
- reproduce representative repository builds/tests;
- establish Cybersand CPU-side baseline;
- exercise sanitizer/replay/soak workloads;
- define resource and timeout limits for automated jobs.

## Phase 5 — orchestration role

- create unprivileged automation accounts;
- integrate Interloc/agent worker services as appropriate;
- evaluate self-hosted GitHub runner threat model before enabling it;
- implement build/artifact cache policies;
- demonstrate end-to-end automated task execution and cancellation.

## Phase 6 — resilience and external complements

- external encrypted backup and restore test;
- optional cheap storage/seedbox tier;
- optional external VPS rendezvous/control node;
- optional hourly burst workers;
- Wake-on-LAN/power scheduling if useful.

## Phase 7 — optimisation

Only after stable evidence exists:

- tune CPU power/performance policy;
- tune compiler/build caching;
- investigate storage upgrade if I/O is limiting;
- investigate RAM upgrade if memory pressure is limiting;
- decide whether M620 provides useful compute/compatibility value;
- compare local node against external dedicated/shared compute on representative workloads.

## Deferred hardware

The second i7-6700 machine remains outside this roadmap until a separate physical-inspection issue identifies the exposed motherboard package and establishes that powering the system is safe.
