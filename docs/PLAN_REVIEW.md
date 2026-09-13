# Plan review

## Review result

The programme is ready for implementation decomposition. The machine is known-good, the initial scope is narrow enough to qualify safely, and the unknowns can be resolved through non-destructive inventory work before provisioning.

## Corrections made during review

1. **No immediate reinstall.** Preserve recovery/data/licence state and inventory the current system first.
2. **No assumed Linux distribution.** Select the canonical OS against explicit workload, driver, maintenance and headless-operation criteria.
3. **Separate logical VPN from physical isolation.** WireGuard can be qualified before the second FTTP circuit exists; later FTTP migration is its own task.
4. **Do not confuse VPN encryption with the primary security benefit.** The target is private service reachability plus a separate trust domain, while retaining application authentication.
5. **Treat self-hosted CI as security-sensitive.** Do not enable broad GitHub-triggered execution until the trust model and privilege boundaries are explicit.
6. **Measure variance, not one benchmark.** Repeated representative workloads are required before tuning or external-compute comparisons.
7. **Treat the 256 GB SSD as working storage.** Add capacity guardrails before caches/artifacts can silently consume the system disk.
8. **Require independent backup and restore evidence.** The node must not be its own backup.
9. **Keep the suspect second i7-6700 out of scope.** Similar age/model does not imply identical PCB population or safe power-up.
10. **Defer hardware purchases/upgrades.** RAM, SSD, networking and GPU changes need evidence of an actual bottleneck or role.

## Risks to revisit

- exact workstation/motherboard and firmware are still unknown;
- SSD age/health may alter provisioning priorities;
- Quadro M620 Linux driver support/maintenance path must be checked when selecting the OS;
- second FTTP availability/router capabilities are external dependencies;
- public self-hosted CI can be dangerous if untrusted code reaches a privileged runner;
- external storage/seedbox providers must not become the sole copy of important data.
