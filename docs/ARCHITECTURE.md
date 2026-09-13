# Target architecture

## Near-term role

The known-good i7-6700 node should become a **private automation/development worker** that can run builds, tests, long simulations, repository tooling and selected orchestration services while remaining recoverable and measurable.

## Trust domains

Preferred eventual topology:

```text
Household FTTP / LAN                 Automation FTTP / LAN
        |                                   |
 household devices                   dedicated router
                                            |
                                    i7-6700 automation node
                                            |
                                      WireGuard overlay
                                            |
                         external VPS / selected remote workers
```

There should be **no route from the automation LAN into the household LAN**. If administration from household devices is required, reach the automation node through an explicitly authenticated overlay/rendezvous path rather than bridging the LANs.

## Node responsibilities

Initially suitable:

- Linux build/test worker;
- Cybersand CPU-side replay, sanitizer, soak and benchmark jobs;
- repository checkout/cache;
- Interloc/agent worker services;
- WireGuard peer;
- monitoring and evidence collection;
- optional self-hosted CI runner, only after threat-model work is complete.

Not initially suitable:

- sole backup location;
- sole control plane for recovery;
- public unauthenticated service host;
- authoritative GPU-performance reference for modern workloads;
- storage archive that consumes most of the 256 GB system SSD.

## External complements

Future infrastructure may include:

- low-cost external VPS for rendezvous/control/failure-domain separation;
- Netcup hourly VPS for clean-room and parallel test workers;
- seedbox/storage host for cheap bulk storage/bandwidth;
- Hetzner Storage Box or equivalent for independent encrypted backup.

These are complements, not prerequisites for first-node qualification.
