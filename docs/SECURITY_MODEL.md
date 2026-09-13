# Security model

## Objective

Make automated/agentic work useful without allowing convenience networking to erase the security benefit of a separate automation environment.

## Primary boundary

The intended strong boundary is a physically separate FTTP connection, router and LAN for automation systems. Do not bridge or route that LAN into the household LAN.

## VPN policy

Use a lightweight private overlay such as WireGuard for administration and machine-to-machine control.

Preferred properties:

- automation node initiates outbound VPN connectivity where practical;
- agent/control services bind only to loopback or VPN/private interfaces;
- public firewall exposes the minimum possible surface;
- VPN keys are unique per peer and revocable;
- application authentication remains enabled even behind the VPN;
- secrets never enter the repository.

## Public ingress

Avoid public ingress by default. If a future service genuinely requires Internet-originated callbacks, isolate a minimal ingress component and authenticate requests cryptographically before forwarding anything internally.

## Privilege model

- normal agent/build work should run unprivileged;
- use dedicated service accounts where practical;
- `sudo` should be explicit and auditable, not blanket passwordless access for arbitrary agent commands;
- containers are not treated as a security boundary by themselves;
- a self-hosted CI runner must not execute untrusted public-fork code with host privileges.

## Update policy

Security updates should be automated or regularly scheduled, but kernel/driver updates that can affect reproducibility should be logged and followed by smoke verification.

## Recovery rule

Remote access must have a documented recovery path for firewall/VPN mistakes. Preserve local console access and avoid making the first VPN/firewall change irreversible remotely.

## Secrets

Store secrets outside Git. Repository content may contain variable names, templates, public keys and setup instructions, but never private keys, passwords, tokens or recovery codes.
