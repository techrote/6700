# Verification gates

The node is not considered production-ready for automated orchestration until all applicable gates pass.

## Gate A — recoverability

- hardware/software inventory exists;
- important pre-existing data/recovery material has been preserved or explicitly declared unnecessary;
- local console recovery works;
- storage health has no unexplained critical condition.

## Gate B — hardware health

- memory test completed without unexplained errors;
- sustained CPU load completes without thermal throttling or instability;
- GPU/SSD temperatures remain within sensible operating limits;
- no unexplained machine-check, storage or PCIe errors remain.

## Gate C — reproducible baseline

- CPU, memory, storage and network baselines recorded;
- repeated measurements show an understood variance envelope;
- a representative repository workload completes successfully.

## Gate D — secure networking

- approved VPN/private overlay works;
- administrative/agent services are not unnecessarily exposed publicly;
- firewall state is documented;
- there is no route from automation LAN into household LAN;
- recovery from VPN/firewall mistakes is documented.

## Gate E — provisioning

- bootstrap/setup process is documented and substantially reproducible;
- versions and configuration are recorded;
- secrets are external to Git;
- reboot leaves required services healthy.

## Gate F — operations

- monitoring and disk-space guardrails are active;
- backup of important configuration/data has been demonstrated;
- restore procedure has been tested on at least a representative sample;
- update/reboot and service-recovery procedures are documented.

## Gate G — agent workload

- unprivileged worker account exists;
- representative automated job succeeds end-to-end;
- job logs/evidence are retained;
- cancellation/timeouts/resource limits work;
- self-hosted CI, if enabled, follows the repository threat model and does not accept untrusted public-fork execution with host privilege.
