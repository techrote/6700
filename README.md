# 6700

Repository-native plan and evidence store for turning the known-good **Intel Core i7-6700 / 16 GB / 256 GB SSD / NVIDIA Quadro M620** machine into a safe, measurable, remotely usable automation and development node.

## Current scope

The programme starts with **one known-good machine only**. A second similarly aged i7-6700 system exists, but it has an unidentified exposed motherboard package and **must not be assumed safe to power or included in implementation work** until a separate inspection clears it.

The first node is intended to become useful for:

- repository builds, tests, packaging and long-running jobs;
- Cybersand CPU-side development, replay, sanitizer and soak workloads;
- agentic orchestration / Interloc-style services;
- secure remote access over a private VPN overlay;
- hardware and software benchmarking with retained evidence;
- later participation in a physically isolated automation LAN on a second FTTP connection.

## Programme principles

1. **Inventory before modification.** Capture the existing hardware, firmware, storage health, operating system and recovery state before reinstalling or changing roles.
2. **Baseline before optimisation.** Measure idle/load power, thermals, clocks, storage, memory, network and representative workloads before tuning.
3. **Security by topology.** Prefer a separate physical Internet/LAN trust domain for automation. Do not create routes from the automation LAN into the household LAN.
4. **Private-by-default services.** Administrative and agent-facing services should bind to private/VPN interfaces wherever practical.
5. **Evidence over assumptions.** Store commands, versions, measurements, logs and conclusions in the repository.
6. **Reproducible provisioning.** Convert successful manual setup into scripts/configuration only after the baseline and requirements are understood.
7. **No premature hardware churn.** Do not replace the M620, SSD, OS, cooling or networking until measurements show a reason.

## Reference pack

Start with [`docs/RAG_INDEX.md`](docs/RAG_INDEX.md). It points implementation agents to narrowly scoped, retrieval-friendly documents.

## Execution

GitHub issues are the executable work queue. Each issue contains a self-contained implementation prompt, prerequisites, acceptance criteria and evidence requirements.
