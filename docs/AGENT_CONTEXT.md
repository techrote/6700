# Agent context

## Mission

Convert the known-good i7-6700 workstation into a dependable, measured and securely reachable development/automation node without destroying useful baseline evidence or prematurely optimising the hardware.

## Known machine facts

- CPU: Intel Core i7-6700.
- Memory: 16 GB.
- Primary storage: 256 GB SSD.
- GPU: NVIDIA Quadro M620.
- Machine is known to boot/work.
- A future second FTTP connection from a different ISP is being considered specifically to isolate automated agentic infrastructure from the household network.

Everything else must be inventoried rather than guessed.

## Explicit exclusions

- Do not work on or power the second suspect i7-6700 system unless a separate issue clears it.
- Do not assume a particular Linux distribution before the inventory/recovery phase establishes constraints.
- Do not expose Interloc, agent RPC, dashboards, databases or SSH directly to the public Internet unless an issue documents why this is required.
- Do not make performance claims from a single run or from workloads affected by thermal throttling, background updates, power-saving transitions or storage exhaustion.
- Do not replace working hardware merely because newer hardware exists.

## Priority order

1. Preserve recoverability.
2. Inventory hardware/firmware/software.
3. Establish baseline health and performance.
4. Establish secure network topology and remote access.
5. Provision repeatably.
6. Validate representative development workloads.
7. Add orchestration/runner roles.
8. Tune only from measured evidence.
9. Add optional storage/burst/external infrastructure later.

## Implementation style

Each change should be small enough to verify independently. Record what changed, why, how to reproduce it, how to reverse it, and what evidence proves it worked.
